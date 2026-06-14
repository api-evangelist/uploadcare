# Uploadcare GraphQL Schema

This is a conceptual GraphQL schema for the [Uploadcare](https://uploadcare.com/) platform, derived from the [Uploadcare REST API](https://uploadcare.com/api-refs/rest-api/), the [Upload API](https://uploadcare.com/api-refs/upload-api/), and the [CDN & Image Transformation API](https://uploadcare.com/docs/transformations/image/).

Uploadcare is a file uploading and processing platform that provides REST APIs for file management, CDN delivery, image transformations, document conversion, video encoding, and malware scanning.

## Schema File

- [uploadcare-schema.graphql](uploadcare-schema.graphql)

## Types

The schema models the full surface area of the Uploadcare platform across the following domains:

### File Management
| Type | Description |
|------|-------------|
| `File` | Top-level file wrapper with status and URL |
| `FileDetails` | Full file details including all metadata, status, and variants |
| `FileInfo` | Core file info used in nested contexts |
| `FileStatus` | Enum: `STORED`, `READY`, `REMOVED`, `WAITING`, `FAILED`, `UNKNOWN` |
| `FileName` | Original and sanitized file name with extension |
| `FileSize` | File size in bytes, kilobytes, and megabytes |
| `MimeType` | MIME type with category and subtype |
| `FileURL` | CDN, original, and signed URL bundle |
| `CDNUrl` | CDN base URL with optional transformation path |
| `OriginalUrl` | The original upload URL |
| `FileConnection` | Paginated list of `FileDetails` |

### Upload
| Type | Description |
|------|-------------|
| `UploadDetails` | Full details of an upload session |
| `Uploader` | Identifies the upload origin (type, name, user-agent) |
| `UploadToken` | Temporary token used for upload authorization |
| `UploadSession` | Single-file upload session with token and URL |
| `MultipartSession` | Multipart upload session with presigned part URLs |

### Groups
| Type | Description |
|------|-------------|
| `Group` | Top-level file group |
| `GroupDetails` | Full group info including file count and dates |
| `GroupFiles` | Files contained in a group with aggregate size |
| `GroupURL` | CDN and API URLs for a group |
| `GroupConnection` | Paginated list of `GroupDetails` |

### Transformations
| Type | Description |
|------|-------------|
| `Transformation` | Top-level transformation wrapper |
| `TransformationDetails` | Status, timing, and error info for a transformation |
| `ImageTransform` | Image transformation parameters and result URL |
| `VideoTransform` | Video conversion parameters and result URL |
| `DocumentTransform` | Document conversion parameters and result URL |
| `Resize` | Width, height, and resize mode |
| `Crop` | Dimensions and offset for cropping |
| `Grayscale` | Toggle grayscale conversion |
| `Rotate` | Rotation angle (90, 180, 270, auto) |
| `Flip` | Vertical flip toggle |
| `Flop` | Horizontal flip toggle |
| `Overlay` | Overlay a second image on top of the source |
| `Blur` | Blur strength and radius |
| `Preview` | Preview size constraints |
| `Format` | Target image format |
| `AutoFormat` | Automatic format selection with fallback |
| `AutoCompress` | Automatic compression with optional quality target |

### Webhooks
| Type | Description |
|------|-------------|
| `Webhook` | Top-level webhook with status and event |
| `WebhookDetails` | Full webhook configuration |
| `WebhookEvent` | Enum: `FILE_UPLOADED`, `FILE_STORED`, `FILE_DELETED`, `FILE_INFO_UPDATED`, `GROUP_CREATED` |
| `WebhookStatus` | Enum: `ENABLED`, `DISABLED` |
| `WebhookConnection` | Paginated list of `Webhook` |

### Projects & Collaborators
| Type | Description |
|------|-------------|
| `Project` | Top-level project with keys and collaborators |
| `ProjectDetails` | Project configuration including pub key and settings |
| `Collaborator` | A project collaborator with role and join date |
| `CollaboratorRole` | Role name and associated permissions |

### Auth & Security
| Type | Description |
|------|-------------|
| `Auth` | Auth state with validation |
| `AuthDetails` | Scheme, public key, signature, and expiry |
| `SecureDelivery` | CDN secure delivery configuration |
| `SignedURL` | Time-limited signed delivery URL |
| `SecureURL` | Original URL paired with its signed counterpart |
| `APIKey` | Public/secret key pair with optional label |
| `PublicKey` | Public API key value |
| `SecretKey` | Secret key hint and creation date |

### CDN
| Type | Description |
|------|-------------|
| `CDN` | Top-level CDN configuration |
| `CDNDetails` | Base URL, CNAME, geo-distribution, and cache settings |

### Metadata & App Data
| Type | Description |
|------|-------------|
| `MetaData` | Key-value metadata entries with optional schema |
| `MetaDataSchema` | Schema definition for a metadata key |
| `AppData` | Application-specific data stored with a file |
| `AppDetails` | App name, version, and description |

## Queries

| Query | Description |
|-------|-------------|
| `file(uuid)` | Fetch a single file by UUID |
| `files(...)` | Paginated file list with filters |
| `group(id)` | Fetch a single file group |
| `groups(...)` | Paginated group list |
| `webhook(id)` | Fetch a single webhook |
| `webhooks` | List all webhooks |
| `project` | Current project info |
| `cdn` | CDN configuration |
| `fileMetadata(uuid, key)` | File metadata |
| `fileAppData(uuid, appName)` | File app data |
| `transformation(id)` | Transformation status and results |
| `secureUrl(uuid, ttl)` | Generate a signed delivery URL |

## Mutations

| Mutation | Description |
|----------|-------------|
| `storeFile(uuid)` | Permanently store a file |
| `deleteFile(uuid)` | Delete a file |
| `copyFile(uuid, target, makePublic)` | Copy to remote storage |
| `createGroup(fileUuids)` | Create a file group |
| `storeGroup(id)` | Permanently store a group |
| `deleteGroup(id)` | Delete a group |
| `createWebhook(...)` | Register a new webhook |
| `updateWebhook(...)` | Update a webhook |
| `deleteWebhook(id)` | Remove a webhook |
| `setFileMetadata(uuid, key, value)` | Set a metadata entry |
| `deleteFileMetadata(uuid, key)` | Remove a metadata entry |
| `transformImage(uuid, operations)` | Apply image transformations |
| `convertVideo(uuid, targetFormat, quality)` | Convert video format |
| `convertDocument(uuid, targetFormat, page)` | Convert document format |
| `startMultipartUpload(...)` | Begin a multipart upload session |
| `completeMultipartUpload(uuid)` | Finalize a multipart upload |

## References

- REST API Reference: https://uploadcare.com/api-refs/rest-api/
- Upload API Reference: https://uploadcare.com/api-refs/upload-api/
- CDN & Image Transformations: https://uploadcare.com/docs/transformations/image/
- Documentation: https://uploadcare.com/docs/
