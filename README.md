
# GitHub File Deleter

A powerful web-based tool for batch deleting multiple files and folders from GitHub repositories with a streamlined dark interface.

## 🌟 Features

- **Streamlined User Flow**: Token → Repository → Branch → Auto-load Files → Select → Delete
- **Dark Mode Interface**: Beautiful dark theme optimized for extended use
- **Batch Operations**: Select and delete multiple files and folders at once
- **Real-time File Tree**: Interactive file browser with folder expansion/collapse
- **Smart Selection**: Select individual files or entire folders with child selection
- **Token Generation**: Direct link to GitHub token creation with proper scopes
- **Progress Tracking**: Real-time status updates during deletion operations
- **Responsive Design**: Works seamlessly on desktop and mobile devices

## 🚀 Getting Started

### Prerequisites

- A GitHub account
- A GitHub Personal Access Token with `repo` scope

### Usage

1. **Generate Token** (if needed):
   - Click the "Generate Token" button
   - This opens GitHub's token creation page with pre-configured settings
   - Copy the generated token

2. **Enter Token**: 
   - Paste your GitHub Personal Access Token
   - Repositories will automatically load

3. **Select Repository**:
   - Choose from your available repositories
   - Branches will automatically load

4. **Select Branch**:
   - Choose the target branch (main/master selected by default)
   - File tree will automatically load

5. **Select Files**:
   - Use checkboxes to select individual files
   - Select folder checkboxes to select all contained files
   - Use "Select All" or "Clear Selection" for bulk operations

6. **Delete Files**:
   - Enter a commit message (optional)
   - Click "Delete Selected Files"
   - Confirm the operation
   - Monitor progress in the status panel

## 🔐 Security

- **No Data Storage**: Your token is never stored or transmitted except to GitHub's API
- **Client-Side Only**: All operations run in your browser
- **Secure Token Handling**: Token input uses password field for privacy
- **Proper Scopes**: Generated tokens include only necessary permissions

## 🛠️ Technical Details

### Built With
- **Pure Vanilla JavaScript**: No frameworks or dependencies
- **GitHub REST API v3**: Direct integration with GitHub's API
- **CSS Grid & Flexbox**: Modern responsive layout
- **Custom CSS Variables**: Consistent dark theme implementation

### API Endpoints Used
- `GET /user/repos` - List user repositories
- `GET /repos/{owner}/{repo}/branches` - List repository branches  
- `GET /repos/{owner}/{repo}/git/trees/{sha}` - Get file tree
- `DELETE /repos/{owner}/{repo}/contents/{path}` - Delete files

### Token Requirements
Your GitHub Personal Access Token needs the following scope:
- `repo` - Full control of private repositories (required for file deletion)

## 📁 Project Structure

```
github-file-deleter/
├── index.html          # Main application file
├── README.md          # This documentation
├── src/
│   └── styles/        # CSS stylesheet modules (unused in this implementation)
└── public/            # Static assets
```

## 🎨 Customization

The application uses CSS custom properties for theming. Key color variables:

```css
:root {
  --gray-1: #111111;    /* Primary background */
  --gray-12: #eeeeee;   /* Primary text */
  --violet-9: #6366f1;  /* Primary accent */
  --blue-9: #3b82f6;    /* Secondary accent */
  --red-9: #ef4444;     /* Danger actions */
}
```

## ⚠️ Important Notes

- **Irreversible Operations**: File deletions cannot be undone
- **Rate Limiting**: GitHub API has rate limits (5000 requests/hour for authenticated users)
- **Large Repositories**: Very large repositories may take time to load
- **Network Dependency**: Requires internet connection for GitHub API access

## 🔧 Troubleshooting

### Common Issues

1. **"Failed to load repositories"**
   - Check your token has `repo` scope
   - Verify token is valid and not expired

2. **"Failed to load file tree"**
   - Ensure branch exists and you have access
   - Check repository permissions

3. **"Delete operation failed"**
   - Verify token has write permissions
   - Check if files are protected by branch rules

### Browser Compatibility
- Modern browsers with ES6+ support
- Chrome 60+, Firefox 55+, Safari 12+, Edge 79+

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## ⚡ Performance Tips

- Use folder selection for bulk operations instead of selecting individual files
- For very large repositories, consider filtering or working with specific folders
- Delete operations are performed sequentially to respect API rate limits

## 🔗 Links

- [GitHub Personal Access Tokens](https://github.com/settings/tokens)
- [GitHub REST API Documentation](https://docs.github.com/en/rest)
- [Repository Contents API](https://docs.github.com/en/rest/repos/contents)
