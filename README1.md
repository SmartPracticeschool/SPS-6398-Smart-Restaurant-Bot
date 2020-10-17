# SPS-6398-Smart-Restaurant-Bot
Smart Restaurant Bot
https://web-chat.global.assistant.watson.cloud.ibm.com/preview.html?region=eu-gb&integrationID=cc7d4b32-f8f3-49bd-9124-54b5a831e21c&serviceInstanceID=0ba8cf75-9dcf-4fbd-9242-df5cc0bbed71{
  "intents": [
    {
      "intent": "Enquiry",
      "examples": [
        {
          "text": "Can you provide me with the menu"
        },
        {
          "text": "Do you have any offers today?"
        },
        {
          "text": "I want to look into the menu"
        },
        {
          "text": "I want to see the menu"
        },
        {
          "text": "What are specials today?"
        },
        {
          "text": "What are the offers available?"
        },
        {
          "text": "What are the special items in the menu?"
        }
      ],
      "description": ""
    },
    {
      "intent": "Greeting",
      "examples": [
        {
          "text": "Good Afternoon"
        },
        {
          "text": "Good Evening"
        },
        {
          "text": "Good Morning"
        },
        {
          "text": "Hello"
        },
        {
          "text": "Hi"
        }
      ],
      "description": ""
    },
    {
      "intent": "Order",
      "examples": [
        {
          "text": "Can you please place my order"
        },
        {
          "text": "Can you please take the order"
        },
        {
          "text": "I want to place an order"
        }
      ],
      "description": ""
    }
  ],
  "entities": [
    {
      "entity": "enquiry",
      "values": [
        {
          "type": "synonyms",
          "value": "menu",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "offers",
          "synonyms": [
            "deals",
            "discount",
            "discounts"
          ]
        },
        {
          "type": "synonyms",
          "value": "special items",
          "synonyms": [
            "specials"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "greetings",
      "values": [
        {
          "type": "synonyms",
          "value": "Good Afternoon",
          "synonyms": [
            "ga",
            "gud afternoon",
            "gud aftrn"
          ]
        },
        {
          "type": "synonyms",
          "value": "Good Evening",
          "synonyms": [
            "ge",
            "gud evening",
            "gud evng"
          ]
        },
        {
          "type": "synonyms",
          "value": "Good Morning",
          "synonyms": [
            "gm",
            "gud morning",
            "gud mrng"
          ]
        },
        {
          "type": "synonyms",
          "value": "Hi",
          "synonyms": [
            "hai"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "items",
      "values": [
        {
          "type": "synonyms",
          "value": "Chicken Biriyani",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Chicken Lollipop",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Egg Biriyani",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Schezwan Paneer",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Veg Biriyani",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "order",
      "values": [
        {
          "type": "synonyms",
          "value": "order",
          "synonyms": [
            "buy",
            "orders"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "payment",
      "values": [
        {
          "type": "synonyms",
          "value": "Card",
          "synonyms": [
            "Credit Card",
            "Debit Card"
          ]
        },
        {
          "type": "synonyms",
          "value": "COD",
          "synonyms": [
            "Cash On Delivery"
          ]
        },
        {
          "type": "synonyms",
          "value": "UPI",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "Specials",
      "values": [
        {
          "type": "synonyms",
          "value": "Chicken Lollipop",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Egg Biriyani",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Schezwan Paneer",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "sys-number",
      "values": [],
      "fuzzy_match": true
    }
  ],
  "metadata": {
    "api_version": {
      "major_version": "v2",
      "minor_version": "2018-11-08"
    }
  },
  "dialog_nodes": [
    {
      "type": "standard",
      "title": "Anything else",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "I didn't understand. You can try rephrasing."
              },
              {
                "text": "Can you reword your statement? I'm not understanding."
              },
              {
                "text": "I didn't get your meaning."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "conditions": "anything_else",
      "dialog_node": "Anything else",
      "previous_sibling": "node_4_1602845345304",
      "disambiguation_opt_out": true
    },
    {
      "type": "event_handler",
      "parent": "node_4_1602845345304",
      "event_name": "focus",
      "dialog_node": "handler_1_1602845524141",
      "previous_sibling": "node_9_1602846942086"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_3_1602846401990",
      "context": {
        "payment": "@payment"
      },
      "conditions": "@payment",
      "event_name": "input",
      "dialog_node": "handler_1_1602846401992"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "Can you provide me with the item I want"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_7_1602845525121",
      "event_name": "focus",
      "dialog_node": "handler_2_1602845525152",
      "previous_sibling": "handler_8_1602845525152"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "How many do you want?"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_8_1602846281811",
      "event_name": "focus",
      "dialog_node": "handler_7_1602846281817",
      "previous_sibling": "handler_9_1602846281817"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "We accept COD, Card and UPI. What is your mode of payment?"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_3_1602846401990",
      "event_name": "focus",
      "dialog_node": "handler_7_1602846401992",
      "previous_sibling": "handler_1_1602846401992"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_7_1602845525121",
      "context": {
        "items": "@items"
      },
      "conditions": "@items",
      "event_name": "input",
      "dialog_node": "handler_8_1602845525152"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_8_1602846281811",
      "context": {
        "number": "@sys-number"
      },
      "conditions": "@sys-number",
      "event_name": "input",
      "dialog_node": "handler_9_1602846281817"
    },
    {
      "type": "standard",
      "title": "Specials",
      "parent": "node_7_1602842236677",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "@Specials",
      "dialog_node": "node_10_1602843623906"
    },
    {
      "type": "frame",
      "title": "Order_Bot",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Thank You, your order of $number of $items is placed. Please pay using $payment"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "conditions": "#Order && @order",
      "dialog_node": "node_4_1602845345304",
      "previous_sibling": "node_7_1602842236677"
    },
    {
      "type": "standard",
      "title": "Restaurant_Bot",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "#Greeting || @greetings",
      "dialog_node": "node_5_1602839759830",
      "previous_sibling": "Welcome"
    },
    {
      "type": "standard",
      "title": "Enquiry_Bot",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "#Enquiry || @enquiry",
      "dialog_node": "node_7_1602842236677",
      "previous_sibling": "node_5_1602839759830"
    },
    {
      "type": "standard",
      "title": "Deleting Context",
      "output": {
        "deleted": "<?context.remove('items')?><?context.remove('order')?><?context.remove('payment')?>",
        "generic": [
          {
            "values": [],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_4_1602845345304",
      "conditions": "true",
      "dialog_node": "node_9_1602846942086"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "title": "SPECIAL ITEMS",
            "options": [
              {
                "label": "Chicken Lollipop",
                "value": {
                  "input": {
                    "text": "Chicken Lollipop"
                  }
                }
              },
              {
                "label": "Schezwan Paneer",
                "value": {
                  "input": {
                    "text": "Schezwan Paneer"
                  }
                }
              },
              {
                "label": "Egg Biriyani",
                "value": {
                  "input": {
                    "text": "Egg Biriyani"
                  }
                }
              }
            ],
            "response_type": "option"
          }
        ]
      },
      "parent": "node_7_1602842236677",
      "conditions": "@enquiry:(special items)",
      "dialog_node": "response_4_1602843069701",
      "previous_sibling": "response_5_1602842836015"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It Costs Rs 200/- per plate"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_10_1602843623906",
      "conditions": "@Specials:(Chicken Lollipop)",
      "dialog_node": "response_4_1602843739092"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It costs Rs 350/- per plates "
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_10_1602843623906",
      "conditions": "@Specials:(Egg Biriyani)",
      "dialog_node": "response_4_1602843829346",
      "previous_sibling": "response_5_1602843797323"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "good evening"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_5_1602839759830",
      "conditions": "@greetings:(Good Evening)",
      "dialog_node": "response_5_1602840376000",
      "previous_sibling": "response_9_1602840269825"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "good afternoon"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_5_1602839759830",
      "conditions": "@greetings:(Good Afternoon)",
      "dialog_node": "response_5_1602840395758",
      "previous_sibling": "response_5_1602840376000"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Hi"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_5_1602839759830",
      "conditions": "anything_else",
      "dialog_node": "response_5_1602840446737",
      "previous_sibling": "response_5_1602840395758"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "We are having 20% off on vegetarian"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          },
          {
            "values": [
              {
                "text": "We are having 10% discount on Fast-food"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_7_1602842236677",
      "conditions": "@enquiry:offers",
      "dialog_node": "response_5_1602842836015",
      "previous_sibling": "response_8_1602842351178"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It costs Rs 220/- per plate"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_10_1602843623906",
      "conditions": "@Specials:(Schezwan Paneer)",
      "dialog_node": "response_5_1602843797323",
      "previous_sibling": "response_4_1602843739092"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "title": "MENU",
            "source": "https://pepetonsgrill.com/wp-content/uploads/2018/02/Pepetons-Grill-Restaurant-Menu-00002.jpg",
            "response_type": "image"
          }
        ]
      },
      "parent": "node_7_1602842236677",
      "conditions": "@enquiry:menu",
      "dialog_node": "response_8_1602842351178",
      "previous_sibling": "node_10_1602843623906"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "good morning"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_5_1602839759830",
      "conditions": "@greetings:(Good Morning)",
      "dialog_node": "response_9_1602840269825"
    },
    {
      "type": "slot",
      "parent": "node_4_1602845345304",
      "variable": "$payment",
      "dialog_node": "slot_3_1602846401990",
      "previous_sibling": "slot_8_1602846281811"
    },
    {
      "type": "slot",
      "parent": "node_4_1602845345304",
      "variable": "$items",
      "dialog_node": "slot_7_1602845525121",
      "previous_sibling": "handler_1_1602845524141"
    },
    {
      "type": "slot",
      "parent": "node_4_1602845345304",
      "variable": "$number",
      "dialog_node": "slot_8_1602846281811",
      "previous_sibling": "slot_7_1602845525121"
    },
    {
      "type": "standard",
      "title": "Welcome",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Hello. I am a Restaurant Bot capable of showing menu, find offers, place orders. How may I help you?"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "conditions": "welcome",
      "dialog_node": "Welcome"
    }
  ],
  "counterexamples": [],
  "system_settings": {
    "off_topic": {
      "enabled": true
    },
    "disambiguation": {
      "prompt": "Did you mean:",
      "enabled": true,
      "randomize": true,
      "max_suggestions": 5,
      "suggestion_text_policy": "title",
      "none_of_the_above_prompt": "None of the above"
    },
    "system_entities": {
      "enabled": true
    },
    "human_agent_assist": {
      "prompt": "Did you mean:"
    },
    "spelling_auto_correct": true
  },
  "learning_opt_out": false,
  "name": "My first skill",
  "language": "en",
  "description": ""
}
