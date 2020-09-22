<div align="center">

## A "Delay\(\)" function for c\+\+ windows applications


</div>

### Description

This code stops your program in windows without causing it to "hang"
 
### More Info
 
Time in milliseconds.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Brian G](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/brian-g.md)
**Level**          |Beginner
**User Rating**    |4.7 (47 globes from 10 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__3-23.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/brian-g-a-delay-function-for-c-windows-applications__3-411/archive/master.zip)





### Source Code

```
void Delay(DWORD nTimeMs)
{
	MSG msg;
	DWORD endTick;
	endTick = GetTickCount() + nTimeMs;
	while(GetTickCount() < endTick)
	{
		if(PeekMessage(&msg, NULL, 0, 0, TRUE))
		{
			TranslateMessage(&msg);
			DispatchMessage(&msg);
		}
	}
	return;
}
```

