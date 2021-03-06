
# [컨트롤 테이블](#컨트롤-테이블)
Control Table은 다이나믹셀 내부에 존재하는 값으로서 다이나믹셀의 현재 상태와 구동에 관한 Data로 구성되어 있습니다.  
사용자는 Instruction Packet을 통해 Control Table의 Data를 변경하는 방식으로 다이나믹셀을 제어할 수 있습니다.

## [컨트롤 테이블, 데이터, 주소](#컨트롤-테이블-데이터-주소)
Control Table은 다이나믹셀의 상태와 제어를 위한 다수의 Data 필드로 구성된 집합체입니다.  
사용자는 READ Instruction Packet을 통해 Control Table의 특정 Data를 읽어서 다이나믹셀의 상태를 파악할 수 있습니다.  
또한 WRITE Instruction Packet을 통해 Control Table의 특정 Data를 변경함으로써 다이나믹셀을 제어할 수 있습니다.  
Address는 Instruction Packet으로 Control Table의 특정 Data를 접근할 때 사용하는 고유값입니다.  
다이나믹셀의 Data를 읽거나 쓰기 위해서는 Instruction Packet에 해당 Data의 Address를 지정해 주어야 합니다.  
Packet에 대한 자세한 내용은 [Protocol 1.0]을 참고해주세요.

`Note` 음수의 표현 방법은 2의 보수(Two’s complement) 규칙을 따릅니다. 2의 보수에 대한 자세한 설명은 위키피디아의 [Two's complement]를 참고하세요.
{: .notice}

### [영역 (EEPROM, RAM)](#영역-eeprom-ram)
Control Table은 2가지 영역으로 구분됩니다. RAM Area에 위치한 Data는 전원이 인가될 때마다 다시 초기값으로 설정됩니다(Volatile).  
반면 EEPROM Area에 위치한 Data는 값을 변경하면 전원이 꺼져도 그 값이 보존됩니다(Non-Volatile).  
**EEPROM Area에 위치한 모든 Data는 Torque Enable(24)의 값이 '0'일 때만 변경할 수 있습니다.**

### [크기](#크기)
Data의 Size는 용도에 따라 1 ~ 2 byte로 정해져 있습니다. Instruction Packet을 통해 Data를 변경할 때는 해당 Data의 Size를 확인하시기 바랍니다.  
2 byte 데이터는 [Little Endian] 규칙에 의해 기록됩니다.

### [접근권한](#접근권한)
Control Table의 Data는 2가지 접근 속성을 갖습니다. ‘RW’는 읽기와 쓰기 접근이 모두 가능합니다. 반면 ‘R’은 읽기 전용(Read Only) 속성을 갖습니다.  
읽기 전용 속성의 Data는 WRITE Instruction으로 값이 변경되지 않습니다.  
읽기 전용 속성(‘R’)은 주로 측정 또는 모니터링 용도로 사용되고, 읽기 쓰기 속성(‘RW’)은 다이나믹셀의 제어 용도로 사용됩니다.

### [초기값](#초기값)
다이나믹셀에 전원이 인가될 때, Control Table의 각 Data는 초기값으로 설정됩니다.  
매뉴얼에 표기된 EEPROM 영역의 Default Value는 제품의 초기 설정값(공장 출하 설정값)입니다.  
사용자가 변경한 경우, 초기값은 사용자가 변경한 값으로 적용됩니다.  
RAM 영역의 Default Value 값은 전원이 인가되었을 때 설정되는 값입니다.

[Protocol 1.0]: /docs/kr/dxl/protocol1/
[Two's complement]: https://en.wikipedia.org/wiki/Two%27s_complement
[Little Endian]: https://en.wikipedia.org/wiki/Endianness#Little
