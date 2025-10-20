# Home URL Buddy - Portable Bookmark Manager

A simple, secure, and portable HTML bookmark manager designed for managing server endpoints and URL extensions. Perfect for customer servers and local development environments.

## Features

🔗 **Simple URL Management**
- Input and save base URLs (IP addresses or domain names)
- Automatically generate clickable links with extensions
- Clean, professional interface

🛡️ **Security & Portability**
- Single HTML file - no external dependencies
- Local storage only - no data sent to external servers
- Works offline completely
- Easy to deploy on any server or local machine

📱 **Responsive Design**
- Works on desktop, tablet, and mobile devices
- Touch-friendly interface
- Modern, clean design

⚙️ **Customizable**
- Add/remove URL extensions dynamically
- Pre-configured with common server endpoints
- Export/import configuration (planned feature)

## Pre-configured Endpoints

Based on your `HomeUrls.csv`, the following endpoints are pre-configured:

- `:5000/devices` - Home Landing page
- `:3000/login` - Grafana Login  
- `:5000/home/guardian` - Guardian Home
- `:5000/home/discoveryservice` - Discovery Service
- `:8222` - NATS Server Monitoring
- `:9200` - Portainer Management UI
- `:41000` - EasyNmos Dashboard

## How to Use

1. **Set Base URL**: Enter your server's IP address or domain (e.g., `http://10.187.134.35`)
2. **Save**: Click "Save Base URL" to store it locally
3. **Access Links**: All configured endpoints will appear as clickable cards
4. **Manage Extensions**: Add or remove URL extensions as needed

## Installation & Deployment

### Local Use
1. Open `index.html` in any modern web browser
2. Bookmark the page for easy access

### Server Deployment
1. Copy `index.html` to your web server
2. Access via `http://yourserver/path/to/index.html`
3. No additional configuration required

### Customer Servers
- Single file deployment
- No database required
- No server-side processing needed
- Works with any web server (Apache, Nginx, IIS, etc.)

## Browser Compatibility

- Chrome 60+
- Firefox 60+
- Safari 12+
- Edge 79+

## Security Notes

- All data stored locally in browser's localStorage
- No external API calls or data transmission
- No cookies or tracking
- Self-contained with no dependencies

## File Structure

```
homeUrlBuddy/
├── index.html          # Main application (self-contained)
├── HomeUrls.csv       # Original URL data (reference)
└── README.md          # This file
```

## Customization

### Adding New URL Extensions

1. Use the "Manage URL Extensions" section in the app
2. Enter the extension path (e.g., `:8080/admin`)
3. Add a description
4. Click "Add Extension"

### Modifying Default Extensions

Edit the `urlExtensions` array in the JavaScript section of `index.html`:

```javascript
let urlExtensions = [
    { path: ':5000/devices', description: 'Home Landing page' },
    // Add your extensions here
];
```

## Keyboard Shortcuts

- `Ctrl + Enter`: Save base URL
- `Enter` in base URL input: Save base URL
- `Enter` in extension path: Move to description field
- `Enter` in description field: Add extension

## Future Enhancements

- [ ] Export/import configuration to JSON
- [ ] Dark mode toggle
- [ ] URL validation with ping test
- [ ] Bulk import from CSV
- [ ] Custom themes
- [ ] URL grouping/categories

## Support

This is a standalone application with no external dependencies. If you encounter issues:

1. Ensure you're using a modern web browser
2. Check browser console for JavaScript errors
3. Verify localStorage is enabled in your browser

## Development Guidelines

### Guard Rails for Code Changes

When making modifications to this application, please follow these principles:

#### 🎯 **Minimal Change Principle**
- **Only change the minimum amount of code necessary** to implement the requested feature or fix
- Avoid refactoring unrelated code unless explicitly requested
- Preserve existing functionality and behavior
- Maintain the single-file architecture unless there's a compelling reason to split

#### 🔒 **Code Stability Guidelines**
- Test changes in isolation before implementing
- Ensure backward compatibility with existing localStorage data
- Preserve the authentication system and security model
- Maintain responsive design across all screen sizes

#### 📝 **Change Documentation**
- Document any breaking changes or new dependencies
- Update this README if new features affect user workflow
- Note any changes to the default URL extensions or authentication

#### 🚫 **What NOT to Change**
- Core authentication mechanism (unless security improvement)
- LocalStorage data structure (maintain backward compatibility)
- Basic UI layout and responsive breakpoints
- Default URL extensions without user request
- Single-file architecture (unless specifically requested)

#### ✅ **Safe Change Areas**
- Adding new features within existing sections
- Improving error messages and user feedback
- Enhancing existing functionality
- Adding new URL extensions or management features
- UI/UX improvements that don't break existing workflows

### Development Workflow
1. **Identify the minimal scope** of changes needed
2. **Test changes locally** before committing
3. **Preserve existing functionality** - don't break what works
4. **Document any new features** or significant changes
5. **Maintain single-file simplicity** unless there's a compelling reason to split

## License

This project is open source and available for modification and distribution.