# Historical Docker build disabled

The former default Dockerfile used Go 1.9.2 and Debian Stretch. Both are unsupported and the image predates the eMudhra certificate-authority compromise and subsequent Go security fixes.

The build is retained as `Dockerfile.legacy-UNSAFE` for historical reference. It is intentionally excluded from the default Docker build path; do not use it to create a deployment. No running deployment of this fork was identified in the cockpit fleet inventory.

Restoring deployment support requires a migration to supported Go, operating-system and InfluxDB versions, followed by application and data-compatibility testing. Preserve database volumes and backups during that migration. Updating only the compiler tag does not establish that this historical server is safe.
