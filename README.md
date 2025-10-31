# ZAP Wallet Chrome Extension 🦊
Zap Wallet

The First AI Wallet on Solana. 

https://zapzip.fun/
https://x.com/zapzipwallet
**The Fun Way to Create and Manage Solana Wallets!**

A Chrome extension that makes Solana wallet creation and management accessible to everyone with AI-powered features and a colorful, engaging interface.

## Features

### 🎯 **Core Features**
- **Wallet Creation**: Generate secure Solana wallets with BIP44 compatibility
- **Local Storage**: All wallet data stored locally in Chrome storage
- **Export/Import**: Export wallet data as text files
- **Phantom Compatible**: Works with Phantom and other Solana wallets
- **No Backend Required**: Fully client-side operation

### 🚀 **Coming Soon Features**
- **Send SOL**: Transfer SOL to other wallets
- **Receive SOL**: Generate QR codes for receiving SOL
- **Token Swaps**: Swap between different Solana tokens
- **DeFi Integration**: Connect to Solana DeFi protocols

## Installation

### For Development
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/zap-wallet-extension.git
   cd zap-wallet-extension
   ```

2. **Load in Chrome**:
   - Open Chrome and go to `chrome://extensions/`
   - Enable "Developer mode"
   - Click "Load unpacked" and select the extension folder

### For Users (Chrome Web Store)
- Search for "ZAP Wallet" in the Chrome Web Store
- Click "Add to Chrome"
- Pin the extension to your toolbar for easy access

## Usage

### Creating Your First Wallet
1. **Click the ZAP Wallet icon** in your Chrome toolbar
2. **Click "Create New Wallet"** to start the process
3. **Write down your seed phrase** safely (12 words)
4. **Your wallet is ready!** You can now export it or use it with other Solana wallets

### Managing Wallets
- **View Address**: Your wallet address is displayed in the popup
- **Copy Address**: Click the copy button to copy your address
- **Show Seed Phrase**: Click to view your 12-word seed phrase
- **Export Wallet**: Download a text file with all wallet information
- **Create Another**: Create additional wallets as needed

### Security Features
- **Local Storage Only**: All data stays on your device
- **No Tracking**: We don't collect any personal information
- **Secure Generation**: Uses proper BIP39/BIP44 standards
- **Export Safety**: Always backup your seed phrase

## Technical Details

### Architecture
- **Manifest V3**: Uses the latest Chrome extension standards
- **Service Worker**: Background script for wallet management
- **Chrome Storage**: Local storage for wallet persistence
- **No External Dependencies**: Fully self-contained

### Wallet Generation
- **BIP39 Mnemonics**: 12-word seed phrases
- **BIP44 Derivation**: Standard Solana derivation path (`m/44'/501'/0'/0'`)
- **Ed25519 Keys**: Solana-compatible key generation
- **Base58 Encoding**: Standard Solana address format

### Data Storage
```javascript
// Chrome storage structure
{
  "wallets": [
    {
      "publicKey": "ZAP...",
      "privateKey": "ZAP...",
      "seedPhrase": "word1 word2 ... word12",
      "derivationPath": "m/44'/501'/0'/0'",
      "createdAt": "2024-01-01T00:00:00.000Z"
    }
  ],
  "currentWallet": { /* current wallet object */ },
  "settings": {
    "theme": "default",
    "notifications": true,
    "autoLock": true,
    "lockTimeout": 15
  }
}
```

## Development

### Project Structure
```
zap-wallet-extension/
├── manifest.json              # Extension manifest
├── popup/                     # Extension popup
│   ├── popup.html            # Popup HTML
│   ├── popup.css             # Popup styles
│   ├── popup.js              # Popup logic
│   └── popup-bundle.js       # Webpack bundled code
├── background/                # Background service worker
│   └── background.js         # Background script
├── src/                       # Source files
│   ├── popup-bundle.js       # Bundle entry point
│   └── walletGenerator.js    # Wallet generation logic
├── assets/                    # Icons and images
│   └── icons/                # Extension icons
├── webpack.config.js          # Webpack configuration
└── package.json              # NPM package file
```

### Building
```bash
# Install dependencies
npm install

# Build the extension
npm run build

# The bundled files will be in popup/popup-bundle.js and popup/background-bundle.js
```

### Known Warnings (Safe to Ignore)

When loading the extension, Chrome may show warnings about test key files:
```
This extension includes the key file 'node_modules/public-encrypt/test/test_key.pem'
This extension includes the key file 'node_modules/public-encrypt/test/test_rsa_pubkey.pem'
This extension includes the key file 'node_modules/public-encrypt/test/test_rsa_privkey.pem'
```

**These are safe to ignore** - they're test fixtures from the `public-encrypt` npm package (a dependency of `crypto-browserify`) and are NOT part of your extension's runtime code. They exist in `node_modules` but are never executed or accessible to the extension.

For production releases, you can exclude `node_modules` entirely and only package the built bundles.

### Testing
1. Load the extension in Chrome developer mode
2. Test wallet creation and management
3. Verify data persistence across browser restarts
4. Test export/import functionality

## Chrome Web Store Submission

### Prerequisites
- Google Developer Account ($5 one-time fee)
- Business information and tax details
- Privacy policy and terms of service
- High-quality screenshots and promotional images

### Submission Process
1. **Prepare Assets**:
   - Extension icons (16x16, 32x32, 48x48, 128x128)
   - Screenshots (1280x800, 640x400)
   - Promotional images
   - Privacy policy

2. **Create Listing**:
   - Extension name and description
   - Category and tags
   - Screenshots and promotional images
   - Privacy policy URL

3. **Submit for Review**:
   - Upload extension ZIP file
   - Fill out all required fields
   - Submit for Google review (1-3 business days)

### Store Listing
- **Name**: "ZAP Wallet - AI-Powered Solana Wallet"
- **Description**: "The fun way to create and manage Solana wallets with AI-powered features"
- **Category**: Productivity
- **Tags**: solana, crypto, wallet, defi, nft, blockchain

## Privacy & Security

### Data Collection
- **No Personal Data**: We don't collect personal information
- **Local Storage Only**: All data stays on your device
- **No Tracking**: No analytics or tracking scripts
- **Open Source**: Fully auditable codebase

### Security Measures
- **Local Encryption**: Wallet data encrypted in storage
- **Secure Generation**: Proper cryptographic standards
- **No Network Calls**: No external API calls for wallet generation
- **Regular Updates**: Security patches and improvements

## Support

### Getting Help
- **Documentation**: Check this README for common questions
- **Issues**: Report bugs on GitHub Issues
- **Community**: Join our Discord server
- **Email**: support@zapzipwallet.com

### Common Issues
- **Extension not loading**: Check Chrome developer mode is enabled
- **Wallet not saving**: Check Chrome storage permissions
- **Export not working**: Check browser download permissions
- **Address not matching**: Verify seed phrase is correct

## Roadmap

### Version 1.1 (Next Release)
- **Send SOL**: Transfer SOL to other addresses
- **Receive SOL**: Generate QR codes for receiving
- **Transaction History**: View past transactions
- **Better Icons**: Professional extension icons

### Version 1.2 (Future)
- **Token Swaps**: Swap between Solana tokens
- **DeFi Integration**: Connect to Solana DeFi protocols
- **NFT Support**: View and manage NFT collections
- **Advanced Security**: Hardware wallet integration

### Version 2.0 (Long-term)
- **Mobile App**: iOS and Android versions
- **Cross-Platform Sync**: Sync wallets across devices
- **Advanced Analytics**: Portfolio tracking and insights
- **Social Features**: Share achievements and milestones

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Solana Foundation for the amazing blockchain
- Chrome Extension team for the excellent platform
- Open source community for inspiration and tools

---

**⚠️ Important**: ZAP Wallet is for educational and development purposes. Always follow security best practices when handling cryptocurrency.

**Made with ❤️ by the ZAP Team**
