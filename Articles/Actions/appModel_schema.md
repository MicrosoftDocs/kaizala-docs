`````json-schema
{
    "$schema": "http://json-schema.org/draft-04/schema#",
    "type": "object",
    "properties": {
        "title": {
            "type": "string",
            "description": "The title of the Action form instance. This is displayed on the chat canvas when an Action is instantiated.",
            "maxLength": 32
        },
        "visibility": {
            "enum": ["All", "Admin"],
            "description": "Value specifying whether the response summary is visible to all/some of the end users."
        },
        "isAnonymous": {
            "type": "boolean",
            "description": "When set to true, the responses provided by the end user are made anonymous.",
            "default": false
        },
        "isResponseAppended": {
            "type": "boolean",
            "description": "When set to true, an end user can add multiple responses to the same Action form instance.",
            "default": true
        },
        "questions": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "title": {
                        "type": "string",
                        "description": "Title of the question.",
                        "maxLength": 32
                    },
                    "type": {
                        "enum": ["SingleSelect", "MultiSelect", "Text", "Numeric", "Location", "DateTime", "Image"],
                        "description": "The type of the question."
                    },
                    "options": {
                        "type": "array",
                        "items": {
                            "type": "object",
                            "properties": {
                                "title": {
                                    "type": "string",
                                    "description": "Title of each option when SingleSelect or MultiSelect is used.",
                                    "maxLength": 32
                                }
                            },
                            "required": [
                                "title"
                            ]
                        }
                    }
                },
                "required": [
                    "title",
                    "type"
                ]
            }
        },
        "properties": {
            "type": "array",
            "items": {
                "type": "object",
                "properties": {
                    "name": {
                        "type": "string",
                        "description": "Title of the form property. Form properties can be used to store metadata for a particular form instance.",
                        "maxLength": 32
                    },
                    "type": {
                        "enum": ["SingleSelect", "MultiSelect", "Text", "Numeric", "Location", "DateTime", "Image"],
                        "description": "The type of the property."
                    },
                    "value": {
                        "type": "string",
                        "description": "Initial value of the property.",
                        "maxLength": 32
                    }
                },
                "required": [
                    "name",
                    "type",
                    "value"
                ]
            }
        }
    },
    "required": [
        "title"
    ]
}
`````