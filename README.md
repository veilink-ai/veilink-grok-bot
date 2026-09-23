# Veilink for Grok Bot

> **Pre-release:** The production OAuth client for this plugin is not active
> yet. Installation and sign-in will be available after Veilink announces the
> Grok Bot Marketplace release.

Connect Grok Bot to [Veilink](https://veilink.ai), a private professional network
where people control introductions and contact sharing. This plugin installs a
remote MCP connection to `https://mcp.veilink.ai/`. Veilink hosts the service;
the plugin contains only connection settings, this guide, and the Veilink logo.

## Connect

1. In Grok Bot's **Plugins** panel, find and install **Veilink for Grok Bot**.
2. Choose **Authenticate** on the Veilink connection card. Sign in to your
   Veilink account in the browser and review the consent screen.
3. Return to Grok Bot and confirm the connection is active. Ask it to show
   Veilink help or onboarding status to verify the MCP tools are available.

The connection uses a public OAuth client ID and PKCE. You do not need to paste
an API key, client secret, or OAuth token into Grok Bot. Veilink asks for
`veilink:read`, `veilink:write`, and `offline_access`. The last scope permits
refreshing the connection; it does not let Grok Bot approve an introduction or
share contacts without the ordinary human confirmation steps in Veilink.
You can review and revoke the connection in your Veilink account's **AI agents**
settings.

## Optional automatic follow-up

The MCP connection lets Grok Bot use Veilink tools when you ask it to. If your
Veilink account offers **Grok Bot routine** under **AI agents**, you can also
set up automatic follow-up:

1. Ask Grok Bot to create an Active webhook routine that checks your Veilink
   inbox through the connected MCP when it wakes. Tell it to ask you before
   accepting introductions or sharing contacts.
2. Open the saved routine's details in Grok Bot and copy its POST URL and sender
   key. Save them in Veilink's dedicated **Grok Bot routine** account setting.
   The sender key is a secret; do not paste it into chat or a generic webhook.
3. Send the test wake offered by that setting, then confirm the Bot run finishes
   in its Run history. An HTTP 200 only means the run started.

The routine is optional; installing this plugin does not create or activate one.
See [Cursor's Grok Bot routine guide](https://cursor.com/help/grok-bot/routines)
for the current Grok Bot controls.

## Availability and support

Veilink account creation and hiring positions are currently unavailable in
the EEA, UK, and South Korea. Check the [Veilink Terms](https://veilink.ai/terms)
and [Privacy Policy](https://veilink.ai/privacy) before connecting. For help,
contact [support@veilink.ai](mailto:support@veilink.ai).

This package grants no additional Veilink account permissions. The public
client ID identifies the plugin configuration, not the user's Grok Bot or xAI
identity. The same package can also be installed in Cursor IDE; its client ID
does not attest which host made a request. Veilink account sign-in determines
which person's data is available.
