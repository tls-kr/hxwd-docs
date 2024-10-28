<%*
/* "Meta Template Picker"  idea makers: Bryan Jenksa and Pamela Wang
	This iteration by Alfonso R. Reyes. Houston, Texas.
 */
 // Common properties will be at the top of frontmatter
const common = {
	  name: "Common",
	  fields: `
	    aliases: 
		type: 
		archetype: 
		summary: 
		status: 
	    rating: 
	    up: 
	    related:
	  `
	}
/* List of dictionaries/objects are defined here
   A central place where to control the properties
   
   name:      is the name of the inline-template
   short:     will be used as a prefix for inline-template selection
   long:      will be used for the sub-folder
   datatable: a Dataview table added below the frontmatter
   fields:    properties of the inline-template
*/
const choices = [
  { name: "Collection",
	short: "collect",
	long: "Collections", 
	datatable: getTableUpRelated(),
    fields: `
		tags: map/collection
		archetype: "[[Collections]]"
    `
  },
    
  { name: "Company",
    short: "comp",
    long: "Companies",
    fields: `
	    industry: 
	    country: 
	    address: 
	    website: 
	    linkedin: 
		tags: map/company
		archetype: "[[Companies]]"
    `
  }, 
   
  { name: "Concept",
    short: "concept",
    long: "Concepts",
    fields: `
		tags: map/concept
		archetype: "[[Concepts]]"
    `
  }, 
  
  { name: "Discipline",
    short: "disc",
    long: "Disciplines",
    fields: `
		tags: map/discipline
		archetype: "[[Disciplines]]"
    `
  }, 
    
  { name: "Industry",
    short: "ind",
    long: "Industries",
    datatable: getTableUpRelated(), 
    fields: `
		tags: map/industry
		archetype: "[[Industries]]"
    `
  },     
  
  { name: "Location",
    short: "loc",  
    long: "Locations", 
    datatable: getTableUpRelated(), 
    fields: `
	    country: 
	    state: 
	    region: 
		tags: map/location
		archetype: "[[Locations]]"
    `
  },
  
  { name: "Media",
    short: "med",  
    long: "Media",
    exclude: ["up", "related", "rating"],
    fields: `
		tags: map/media
		archetype: "[[Media]]"
    `
  },
  
  { name: "Object",
    short: "obj",  
    long: "Objects",
    fields: `
		tags: map/object
		archetype: "[[Objects]]"
    `
  },  
  
  { name: "People",
    short: "people",
    long: "People",
    datatable: getTableUpRelated(),
    fields: `
	    known_for: 
	    company: 
	    BU:
	    position: 
	    role: 
	    reports_to: 
	    email: 
	    address: 
	    phone: 
	    city: 
	    linkedin: 
	    github: 
		tags: map/person
		archetype: "[[People]]"
    `
  },    

  { name: "Rating",
    short: "rating",
    long: "Ratings",
    exclude: ["rating", "status", "summary", "up", "related"],
    fields: `
		tags: map/rating
		archetype: "[[Ratings]]"	    
    `
  },

  { name: "Realm",
    short: "realm",  
    long: "Realms",
    exclude: ["rating", "up", "related"],
    fields: `
		tags: map/realm
		archetype: "[[Realms]]"
    `
  },
  
  { name: "Status",
    short: "status",
    long: "Status",  
    exclude: ["rating", "status", "up", "related"],
    fields: `
		tags: map/status
		archetype: "[[Status]]"
    `
  }, 
   
  { name: "Type", 
    short: "type", 
    long: "Types", 
    exclude: ["rating", "status", "up", "related"],
    fields: `
		tags: map/type
		archetype: "[[Types]]"
    `
  },
]

let uuid; let yml; let choice; let commonFields;
let folder = "Atlas";  // this is the parent of sub-folders
// find a prefix match to select dictionary member

let title = tp.file.title;
uuid = get_uuid(true)

if (title.startsWith("Untitled")) {
	// most likely you pressed Ctrl+N (new note)
	title = await tp.system.prompt("Note Name")
	// pressing <Enter> or <Esc >creates "Untitled-20240220104000"
	if (title == null) {
		title = "0" 
	} else if (title.length <= 1) {
	  // if not null, ask for length; looking for <Enter>
		title = "1"
	}
}

 choices.forEach(item => {
	 if (title.startsWith(item.short)) {
		 choice = item; }
})
// if the prefix was found
if (choice) {
	if (choice.exclude) 
		commonFields = removeExcludedKeys(common.fields, choice.exclude)
	else
		commonFields = common.fields
	yml = commonFields + choice.fields + uuid
	yml = cleanFrontmatter(yml);   // remove blank lines, spaces

	title = extractTitle(title); // get rid of the prefix
	await tp.file.rename(title);
	folder = "Atlas/" + choice.long + "/";
	await tp.file.move(folder + title);   // move to sub-folder
	// add frontmatter to the new note
	addFrontmatter(yml);
	// add table view to new note, if defined
	if (choice.datatable) {
		addTableBelowFrontmatter(choice.datatable)
	}
	new Notice("New " + choice.name + " just added ...")
} else {
	/*  Note name prefix was not found in dictionary, 
		or note originally "Untitled" then renamed from prompt, 
		or note is already named but is a link,
		or note produced by <Enter> or <Escape>
	*/
	// append/run the minimal template when note prefix not known
	tR += await tp.file.include("[[Default Minimal Template]]");
	
	if (title == "0" || title == "1") {
		// Name the note "Untitled-" if <Enter>; "untitled-" if <Esc>
		uuid = get_uuid(false)
		title == "1"
	     ? setTimeout(() => {tp.file.rename("Untitled-"+uuid)}, 350)
	     : setTimeout(() => {tp.file.rename("untitled-"+uuid)}, 350)
	} else {
		setTimeout(() => {tp.file.rename(title)}, 350)
	}
}


function cleanFrontmatter(yml) {
	// remove blank lines, spaces and tabs at the start of frontmatter
	const regex = /^(?=\n)$|^\s*|s*$|\n\n+/gm   
	yml = yml.split('\n')
		.map(function(line) {
			return line.replace(regex, "")})
		.filter(function(x) {return x}).join("\n");
	return yml;
}

function get_uuid(wholeProperty) {
	// Make an uuid to time stamp each new note
	return wholeProperty 
				? "uuid: " + "'" 
				   +  tp.file.creation_date("YYYYMMDDHHmmss") + "'"
				: tp.file.creation_date("YYYYMMDDHHmmss")
}

function getTableUpRelated() {
	// Dataview table showing notes 
	let yml = `
	TABLE up, related
	FROM ""
	WHERE up = link(this.file.name)
	   OR contains(related, link(this.file.name))
	SORT file.name ASC
	`
	return yml
}

function addTableBelowFrontmatter(dt) {
		tR += "\n\n"
		tR += "```dataview"
		tR += "\n"
		tR += cleanFrontmatter(dt)
		tR += "\n"
		tR += "```"
		tR += "\n"
}

function addFrontmatter(yml) {
	tR += "---\n"
	tR += yml
	tR += "\n---\n"
}

function extractTitle(title) {
	let result;
	let count = (title.match(/-/g) || []).length;
	let dateRegex = /(\d{4})([-])(\d{2})([-])(\d{2})/;
	
	switch (count) {
		case 0:
			result = title.trim()
			break
		case 1: 
			result = title.split("-").slice(1)[0].trim()
			break
		default:
			result = dateRegex.test(title) && count == 2
				? title.trim() 
				: title.split("-").slice(1).join("-").trim()
	}
	return result;
}

function removeExcludedKeys(txt, exclude) {
	removeList = exclude.map(p => p+":")
	//console.log("removeList:", removeList)
	var expStr = removeList.join("|");
	//console.log("expStr:", expStr)
	return txt
		.replace(new RegExp(expStr, 'gi'), ' ')
		.replace(/\s{2,}/g, '\n')
}
_%>