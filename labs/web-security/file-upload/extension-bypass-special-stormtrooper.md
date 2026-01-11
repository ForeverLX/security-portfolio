# File Extension Blacklist Bypass

## 🎯 Objective
Bypass file extension blacklist to upload and execute PHP code.

## 🔍 Vulnerability Analysis
- **Type**: File upload with incomplete extension blacklist
- **Target**: `special-stormtrooper.apac01.hackviser.space`
- **Flaw**: Common extensions blocked, uncommon ones allowed
- **Impact**: Remote code execution via alternative PHP extensions

## 💥 Exploitation
1. **Extension Testing**: Created copies with various PHP-executable extensions
2. **Successful Extension**: `.phar` extension not on blacklist, accepted by server
3. **Upload**: PHP web shell uploaded as `.phar` file
4. **Execution**: Successfully accessed and executed commands via the uploaded file

## 🛡️ Mitigation Strategies
1. **Extension Whitelisting**: Only allow specific known-safe extensions
2. **MIME Verification**: Check server-detected MIME type matches extension
3. **Content Analysis**: Validate file content matches claimed type
4. **Regular Updates**: Keep blacklists current with new executable extensions

## 📊 Skills Demonstrated
- **Blacklist Analysis**: Testing and identifying incomplete protection
- **Alternative Extension Usage**: Using non-standard PHP handlers
- **Server Configuration Understanding**: Knowing which extensions execute as PHP

*Conducted in controlled environment for educational purposes*
