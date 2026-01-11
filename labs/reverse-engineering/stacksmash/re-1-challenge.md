# StackSmash re-1 Challenge - Binary Reverse Engineering

## 🎯 Objective
Reverse engineer a 32-bit ELF binary to discover the input that triggers the "correct!" success message, demonstrating fundamental binary analysis and pattern recognition skills.

## 🔍 Binary Analysis
- **File Type:** ELF 32-bit LSB pie executable (Intel 386), not stripped
- **Analysis Tools:** `file`, `strings`, GDB with disassembly
- **Key Findings:** 
  - Binary contains clear success message "correct!" and source file reference "simple.c"
  - Not stripped → function names and symbols preserved
  - Character-by-character comparison loop in disassembly

## 💥 Exploitation Process

### Static Analysis Phase
```bash
# Initial reconnaissance
file re-1
strings re-1 | grep -E "(correct|flag|simple)"

# Disassembly examination
gdb -q re-1
(gdb) disas main
Pattern Recognition
Disassembly revealed a validation loop comparing input against hardcoded hex values:

text
0x66, 0x6c, 0x61, 0x67, 0x7b, 0x62, 0x72, 0x61, 0x6e, 0x63, 0x68, 0x65, 0x73, 
0x5f, 0x69, 0x6e, 0x5f, 0x74, 0x68, 0x65, 0x5f, 0x74, 0x72, 0x65, 0x65, 0x7d
Solution Extraction
python
# Manual hex-to-ASCII conversion
hex_values = [0x66, 0x6c, 0x61, 0x67, 0x7b, 0x62, 0x72, 0x61, 0x6e, 0x63, 
              0x68, 0x65, 0x73, 0x5f, 0x69, 0x6e, 0x5f, 0x74, 0x68, 0x65, 
              0x5f, 0x74, 0x72, 0x65, 0x65, 0x7d]
flag = ''.join(chr(h) for h in hex_values)
print(flag)  # flag{branches_in_the_tree}
Verification
bash
echo -n "flag{branches_in_the_tree}" | ./re-1
# Output: "correct!"
🛡️ Mitigation Strategies
Strip Binaries: Remove debugging symbols with strip --strip-all binary

Obfuscation: Implement control flow obfuscation to hinder static analysis

Runtime Protection: Add anti-debugging techniques and checksums

Input Validation: Move validation logic to server-side where possible

📊 Skills Demonstrated
Static Analysis: ELF file examination and string extraction

Dynamic Analysis: GDB debugging and disassembly interpretation

Pattern Recognition: Identifying validation logic in assembly

Data Conversion: Manual hex-to-ASCII translation

Methodical Approach: Systematic binary analysis workflow

🏆 Competitive Context
Part of challenge series where I achieved 3rd place overall (Top 1.5%) among 204 participants on StackSmash platform

Conducted in controlled environment for educational purposes
