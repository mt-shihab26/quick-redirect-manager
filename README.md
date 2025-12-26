<p align="center">
  <img src="./assets/logo.svg" alt="Quick Redirect Manager Logo" width="200" height="200" />
</p>

<h1 align="center">Quick Redirect Manager</h1>

A lightweight WordPress URL redirection manager plugin that uses WordPress's native options table for storage. Perfect for managing redirects without the overhead of additional database tables.

## Features

- Simple and intuitive WordPress admin interface
- Support for both 301 (permanent) and 302 (temporary) redirects
- Multiple redirection types:
    - Internal path to internal path (`/old-page` → `/new-page`)
    - Internal path to external URL (`/external-link` → `https://example.com`)
- Lightweight - uses WordPress options table (no additional tables)
- Built with performance in mind

## Used By

This plugin is actively used on the following websites:

- [paystubhero.com](https://www.paystubhero.com)

## Usage

1. Go to **Settings → Redirections** in your WordPress admin
2. Find the "Add New Redirection" form
3. Enter your source URL (the URL to redirect from)
4. Enter your target URL (the destination URL)
5. Select the redirect type (301 or 302)
6. Click "Add Redirection"
7. The redirect will be active immediately

![Dashboard](./assets/dashboard.webp)

### Managing Redirects

- **View All Redirects**: All active redirects are displayed in a table on the settings page
- **Delete Redirect**: Click the delete button next to any redirect to remove it
- **Test Redirect**: Navigate to the source URL to verify the redirect works correctly

## Configuration

### Redirect Types

The plugin supports two types of HTTP redirects:

#### 301 - Permanent Redirect

- **Use when**: The original page has permanently moved to a new location
- **SEO Impact**: Passes link equity (ranking power) to the new URL
- **Browser Behavior**: Browsers cache this redirect, so users won't hit your server on subsequent visits
- **Best for**:
    - Permanently moved content
    - Site restructuring
    - URL changes that won't be reversed

#### 302 - Temporary Redirect

- **Use when**: The redirect is temporary or might change
- **SEO Impact**: Does not pass link equity to the new URL
- **Browser Behavior**: Browsers don't cache this redirect, always checking your server
- **Best for**:
    - A/B testing
    - Temporary maintenance pages
    - Seasonal redirects
    - Short-term URL changes

### Redirection Examples

#### Internal to Internal

Redirect from one page on your site to another:

- **Source**: `/old-page` or `/blog/old-post`
- **Target**: `/new-page` or `/blog/new-post`
- **Type**: 301 (if permanent) or 302 (if temporary)

#### Internal to External

Redirect from your site to an external website:

- **Source**: `/external-link` or `/partner`
- **Target**: `https://example.com` or `https://partner-site.com/page`
- **Type**: Usually 302 (temporary)

#### With Query Parameters

The plugin preserves the exact path you specify:

- **Source**: `/product?id=123`
- **Target**: `/new-product?id=123`
- **Note**: Query parameters must match exactly for the redirect to trigger

## Installation

1. Upload the plugin files to `/wp-content/plugins/quick-redirect-manager/`
2. Run `composer install` to install dependencies (if not already installed)
3. Activate the plugin through the 'Plugins' menu in WordPress
4. Configure settings under **Settings → Redirections**

## License

Licensed under the GPL v2 or later - see the [LICENSE](LICENSE) file for details.
