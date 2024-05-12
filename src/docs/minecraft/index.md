# Setting up your is-a.dev domain with a Minecraft server

We do __not__ support SRV records. You must have a dedicated IP and use an A record in order to link your domain to a Minecraft server.
You also cannot run your Minecraft server on any port other than the default port, as that would require an SRV record.
Follow the instructions [here](domain_structure) on how to format your file.

Note that you must use a nested subdomain. This means that you can use, for example, minecraft.uwu.is-a.dev for a minecraft server but you *cannot* use `uwu.is-a.dev` for a Minecraft server.