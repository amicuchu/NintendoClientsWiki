You may be surprised to see the real names of parameter and structure members on many of the pages that describe NEX protocols. NEX has automatically generated the code that encodes/decodes method parameters and structures from a data definition language (DDL), and many games contain the parse tree of the DDL declarations in their data segment. It's encoded in big-endian byte order (regardless of the platform) and looks as follows:

| Type | Description |
| --- | --- |
| Uint32 | Magic number (0xCD652312) |
| Uint8 | Unknown (always 0) |
| Uint32 | Major version |
| Uint32 | Minor version |
| Uint32 | Micro version |
| Uint32 | Build version |
| [NameSpace] | Root namespace |

## NameSpace
| Type | Description |
| --- | --- |
| Uint32 | Number of elements (N) |
| [Element](#element) (N) | Namespace elements |

### Element
| Type | Description |
| --- | --- |
| Uint8 | Type id |
| | Body |

| ID | Type |
| --- | --- |
| 1 | [NameSpaceItem](#namespaceitem) |
| 2 | [Declaration](#declaration) |
| 3 | DOClassDeclaration |
| 4 | DatasetDeclaration |
| 5 | TypeDeclaration |
| 6 | Variable |
| 8 | RMC |
| 9 | Action |
| 10 | AdapterDeclaration |
| 11 | PropertyDeclaration |
| 12 | ProtocolDeclaration |
| 13 | Parameter |
| 14 | ReturnValue |
| 15 | ClassDeclaration |
| 16 | TemplateDeclaration |
| 17 | SimpleTypeDeclaration |
| 18 | TemplateInstance |
| 19 | [DDLUnitDeclaration](#ddlunitdeclaration) |
| 20 | DupSpaceDeclaration |

## String
| Type | Description |
| --- | --- |
| Uint32 | Length (N) |
| Bytes (N) | String (without null terminator) |

## ParseTreeItem
| Type | Description |
| --- | --- |
| [String] | Name |

## NameSpaceItem
The second parse tree item is always the same as the first parse tree item. I don't know why it's stored twice.

| Type | Description |
| --- | --- |
| [ParseTreeItem](#parsetreeitem) | Parse tree item |
| [ParseTreeItem](#parsetreeitem) | Parse tree item |

## Declaration
| Type | Description |
| --- | --- |
| [NameSpaceItem](#namespaceitem) | Name space item |
| [String] | DDL unit name |
| [Namespace] | Properties |

## DDLUnitDeclaration
| Type | Description |
| --- | --- |
| [Declaration] | Declaration |
| [String] | Unit name |
| [String] | Unit dir |

[NameSpace]: #namespace
[Declaration]: #declaration
[String]: #string