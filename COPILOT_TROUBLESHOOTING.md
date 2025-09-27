# GitHub Copilot Troubleshooting Guide for VS Code

## Common Issues and Solutions

### 1. Authentication Issues

#### Check if you're signed in to GitHub
- Open VS Code Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`)
- Run command: `GitHub Copilot: Sign In`
- Follow the authentication flow in your browser
- Verify you're signed in to the correct GitHub account

#### Verify your GitHub account status
- Go to [GitHub Copilot settings](https://github.com/settings/copilot)
- Ensure you have an active Copilot subscription
- Check if your account has access to Copilot (individual, business, or education)

### 2. Extension Issues

#### Install/Update GitHub Copilot Extension
1. Open VS Code Extensions panel (`Ctrl+Shift+X`)
2. Search for "GitHub Copilot"
3. Install or update the official extension by GitHub
4. Restart VS Code after installation

#### Check Extension Status
- Look for the Copilot icon in VS Code status bar (bottom-right)
- Click the icon to see current status
- Should show as "Ready" when working properly

### 3. Settings and Configuration

#### Enable Copilot in VS Code Settings
1. Open Settings (`Ctrl+,` or `Cmd+,`)
2. Search for "copilot"
3. Ensure these settings are enabled:
   - `github.copilot.enable: true`
   - `github.copilot.inlineSuggest.enable: true`

#### Language-Specific Settings
For Java development (relevant to this repository):
```json
{
    "github.copilot.enable": {
        "*": true,
        "java": true,
        "javascript": true,
        "typescript": true
    }
}
```

### 4. Network and Firewall Issues

#### Corporate Networks
- Check if your organization blocks GitHub API calls
- Ensure these domains are accessible:
  - `api.github.com`
  - `copilot-proxy.githubusercontent.com`
- Configure proxy settings if needed in VS Code settings

#### Firewall Settings
- Allow VS Code through Windows Firewall
- Ensure outbound HTTPS (port 443) is allowed

### 5. VS Code and System Issues

#### Update VS Code
- Ensure you're running a recent version of VS Code
- Copilot requires VS Code 1.60.0 or later

#### Clear VS Code Cache
1. Close VS Code
2. Delete the extensions cache folder:
   - Windows: `%USERPROFILE%\.vscode\extensions`
   - macOS: `~/.vscode/extensions`
   - Linux: `~/.vscode/extensions`
3. Reinstall the Copilot extension

### 6. Java-Specific Troubleshooting

Since this repository contains Java code:

#### Java Extension Pack
- Install the Java Extension Pack by Microsoft
- Ensure Java Language Server is running properly
- Check Java version compatibility (Java 8 or higher)

#### Java Project Setup
- Ensure your Java project is properly configured
- Check if `.classpath` and `.project` files exist (for Eclipse projects)
- For Maven/Gradle projects, ensure proper structure

### 7. Quick Diagnostic Steps

1. **Test Copilot with a simple comment:**
   ```java
   // Function to calculate the area of a circle
   ```
   Copilot should suggest code completion

2. **Check the Output panel:**
   - View → Output → Select "GitHub Copilot" from dropdown
   - Look for error messages or warnings

3. **Restart Language Server:**
   - Command Palette → "Java: Restart Language Server"

### 8. Advanced Troubleshooting

#### Reset Copilot Authentication
```
Command Palette → "GitHub Copilot: Reset Auth"
```

#### Check Copilot Logs
1. Help → Toggle Developer Tools
2. Console tab → Look for Copilot-related errors
3. Network tab → Check for failed API calls

#### Manual Token Refresh
1. Go to [GitHub Personal Access Tokens](https://github.com/settings/tokens)
2. Generate a new token with Copilot scopes
3. Sign out and back into Copilot in VS Code

### 9. Alternative Solutions

#### If Copilot Still Doesn't Work:
1. Try the GitHub Copilot Chat extension
2. Use Copilot in GitHub.dev (web editor)
3. Try IntelliJ IDEA with Copilot plugin (for Java development)
4. Contact GitHub Support with your account details

### 10. Subscription and Billing Issues

#### Free Trial Expired
- Check if your free trial has ended
- Purchase a Copilot subscription at [GitHub Copilot](https://github.com/features/copilot)

#### Student/Education Access
- Verify your student status through GitHub Education
- Ensure your educational email is verified

## Getting Help

If none of these solutions work:

1. **GitHub Community Forum:** [GitHub Community Discussions](https://github.com/orgs/community/discussions)
2. **VS Code Issues:** [VS Code GitHub Repository](https://github.com/microsoft/vscode/issues)
3. **Copilot Support:** [GitHub Support](https://support.github.com/)

## Tips for Better Copilot Experience

1. **Write descriptive comments** before functions
2. **Use meaningful variable names**
3. **Keep context clear** in your code
4. **Accept suggestions with Tab key**
5. **Use Ctrl+Right Arrow** to accept word-by-word