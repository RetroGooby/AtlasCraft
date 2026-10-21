# Getting Started

This guide describes the Minecraft standalone preview. The application source
remains private; these are instructions for the packaged Windows application.

## Install The Application

1. Download the Windows application ZIP from the official
   [Releases page](https://github.com/RetroGooby/AtlasWorlds/releases).
2. Extract the entire `AtlasWorldsMinecraft` folder before running anything.
3. Keep `AtlasWorldsMinecraft.exe` and `_internal` together, then open the executable.
4. Expect an empty server library on first run. Existing hub servers are not
   imported automatically.

Do not disable security software or bypass an unknown download warning. Verify
the download's origin before proceeding. A checksum verifies file integrity; it
is not a digital signature or a safety certification.

### Upgrade An Existing Standalone

Stop controlled servers cleanly and close the old standalone before opening the
new version. Extract the new download into a separate folder rather than merging
it into the old application. On the same Windows account, the default application
data and registered server folders are reused; worlds are not recreated. Keep
independent backups of application data and servers before upgrading. Do not run
both application versions against the same server folders.

## Create From A Server-Pack ZIP

1. Download a trusted, dedicated **server pack**, not a client modpack export.
2. Choose **New Server...**, select **Server pack ZIP**, and enter a server name and parent folder.
3. Choose a heap limit that leaves enough memory for Windows and other applications.
4. Wait for **Check Compatibility** and review the detected Minecraft version,
   loader, Java requirement, and any warnings. Resolve unsupported or ambiguous
   requirements before starting setup.
5. Read the [Minecraft EULA](https://www.minecraft.net/en-us/eula). Agree only if
   you accept it, and separately confirm that you trust the pack's executable content.
6. Choose **Create & Start**. Supported setups can obtain the required Java runtime
   and loader. Watch the setup output for progress or actionable errors.
7. Wait for confirmed readiness. Large modpacks can spend many minutes starting.
   You can close the setup dialog after completion; control continues in Overview.

No compatibility checker can prove that a pack is safe or that all its mods work
together. Unknown installers and unsupported layouts fail instead of being run blindly.

## Create From A Server JAR

1. Download a trusted dedicated Java Edition server JAR, such as the vanilla server
   from [Minecraft's official server page](https://www.minecraft.net/en-us/download/server).
2. Choose **New Server...**, select **Server JAR**, and browse to the downloaded file.
3. Enter a server name, destination parent folder, and maximum memory limit.
4. Review the automatic compatibility check. Embedded release metadata identifies
   Minecraft and Java; older JARs without metadata may need a version or Java
   override under **Advanced**.
5. Read and accept the EULA only if you agree, separately confirm trust, then
   choose **Create & Start**. Java is reused or downloaded as needed.

The JAR is copied into a fresh server folder; the downloaded original is unchanged.
Client JARs, individual mods, loader installers, unsupported launchers, and JARs
missing companion files are rejected. Use a complete server-pack ZIP for modpacks.
JAR inspection is limited to 256 MiB. An offline check does not guarantee a
successful first boot or verify external downloads made by a third-party server.

## Import Without Recreating A Server

1. Stop the server cleanly. Disable its old manager's scheduled actions and close
   that manager. Only one manager may control the server folder.
2. Choose **Import Existing...** and select the installed server folder.
3. Choose **Scan Folder**, then review the Minecraft, loader, and Java detection.
4. If Java is missing, select the matching installed Java home: the directory
   containing `bin/java.exe`, not the `bin` folder itself. Scan again.
5. Confirm trust and exclusive control, then choose **Import Server**.
6. Create a full backup and start the server when ready.

Import registers the original folder in place. It does not move the world,
rewrite the server's settings, accept its EULA, or start it automatically.
The server must already be installed; import does not run bootstrap scripts or
download Java. Old-manager schedules, DNS credentials, and app preferences are
not migrated. Configure optional RCON separately in the standalone.

Imported folders are not owned for deletion. **Archive & Remove...** creates a
verified final world archive and unregisters them while leaving their files intact.

## Friends Joining

In **Overview**, select the appropriate address mode and **Copy Address**:

- **This PC:** a Minecraft client running on the server computer.
- **LAN:** a client on the same local network.
- **Friends (Internet):** your public address and this server's game port.

For internet play, forward the displayed **TCP game port** to the server computer
and check its firewall. Public-IP detection does not verify incoming connectivity.
Double NAT, CGNAT, VPNs, and router loopback can affect access.

Optional **Custom Hostname...** setup uses a DuckDNS hostname you claim and authorize.
DNS does not hide your public IP, create a tunnel, or open router ports. Never
forward the RCON administration port to the internet.

## Mods And Friends' ZIPs

1. Open **Mods > Scan Installed** for the selected server.
2. Search a provider and select a version matching the detected Minecraft and loader.
3. Add it to the plan, then **Preview Dependencies**. Review every proposed change.
4. Stop the server before **Back Up & Apply**. Updates and removals also need review.
5. Restart, inspect the log, and test before inviting players back.

Modrinth is the default provider. CurseForge needs your own API key in the app data
folder's `.env` file as `CURSEFORGE_API_KEY=your-key`. Keep this file private.
Provider restrictions can require manual downloads.

**Export Friends' ZIP** describes the current managed additions and removals. It
does not recreate the base modpack. Friends must use the same base pack and loader,
follow the included instructions, and remove obsolete files where indicated.
Do not replace an entire client `mods` folder with this additions ZIP. Respect
mod authors' licenses and provider rules when sharing files.

## Update A Pack

1. Obtain a newer server ZIP for the **same modpack** and stop the server.
2. Choose **Servers > Update Pack from ZIP...**.
3. Review pack identity, versions, warnings, backup, and preservation details.
4. Apply the protected update, then start and verify the updated server.
5. Use **Roll Back Pack...** when recovery is needed and the previous installation
   is available. Preserve progress made since the update before restoring an old world.

Preserving a configuration file does not make an author's breaking changes
compatible. Added mods may also need updates. Keep independent backups outside
the application's retention-managed backup folder.

## Running Multiple Servers

Use **Running Servers** for per-server status, controls, resource information,
and separate server logs. Starting another server checks memory headroom, port
conflicts, and overlapping folders. Leave room for Windows, clients, and startup
overhead; a heap limit is not the process's total memory usage.

Only dashboard-owned servers are controlled. An externally started process is
not automatically adopted or terminated. Starting or stopping one server does not
stop the others, but startup and shutdown operations are serialized. Large packs
may take several minutes to become ready.

## Players And Settings

The **Players** and **Live Settings** tabs require configured local RCON and a
verified ready server. Administrative actions require confirmation. Unsupported
commands stay disabled; commands are not automatically retried after a timeout.
Refresh the state before deciding whether to retry a command yourself.

Use **Settings** for supported `server.properties` changes. **Back Up & Save
Settings** offers to stop, back up the settings, save, and restart only the selected
dashboard-controlled running server. Other servers keep running; a stopped server
stays stopped. Failed stops or saves preserve the draft, and successful saves
clear its unsaved-change warning. Servers started outside this dashboard must be
stopped there first. The settings backup covers `server.properties`, not the entire
server or world. Global PvP changes require a restart. Scheduled actions run while
AtlasWorlds is open; the preview is not a Windows service.

## Data And Recovery

Default application data: `%LOCALAPPDATA%\AtlasWorldsMinecraft`.
Default new-server parent: `%LOCALAPPDATA%\AtlasWorldsMinecraft-Servers`.
Use **Tools > Open Application Data** to find the actual data folder.

Replacing the extracted application folder is not a world migration. Keep the
registry, server folders, and backups safe. Do not delete retained transaction or
rollback folders merely to bypass a recovery warning.

For help, include versions, steps, and a sanitized log excerpt in an
[issue](https://github.com/RetroGooby/AtlasWorlds/issues). See [SECURITY.md](../SECURITY.md)
before uploading any files.
