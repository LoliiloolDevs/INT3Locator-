# INT3Locator-


```C
DWORD locateINT3(){
	DWORD _s = format(0x400000);
	const char i3_8opcode[8] = { 0xCC, 0xCC, 0xCC, 0xCC, 0xCC, 0xCC, 0xCC, 0xCC };
	for (int i = 0; i < MAX_INT; i++){
		if (memcmp((void*)(_s + i), i3_8opcode, sizeof(i3_8opcode))==0){
			return (_s + i);
		}
	}
	return NULL;
}
```
