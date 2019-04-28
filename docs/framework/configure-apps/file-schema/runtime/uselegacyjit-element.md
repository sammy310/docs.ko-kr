---
title: <useLegacyJit> 요소
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a467599084f01b1a48c95c5e25fb1f869156dffa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673890"
---
# <a name="uselegacyjit-element"></a>\<useLegacyJit> 요소

공용 언어 런타임이 Just-In-Time 컴파일에 레거시 64비트 JIT 컴파일러를 사용할지를 결정합니다.  
  
\<configuration>  
\<runtime>  
\<useLegacyJit>
  
## <a name="syntax"></a>구문  
  
```xml
<useLegacyJit enabled=0|1 />
```

요소 이름을 `useLegacyJit` 대/소문자 구분 합니다.
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
| 특성 | 설명                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | 필수 특성입니다.<br><br>런타임이 레거시 64 비트 JIT 컴파일러를 사용 하는지 여부를 지정 합니다. |  
  
### <a name="enabled-attribute"></a>enabled 특성  
  
| 값 | 설명                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | 공용 언어 런타임은.NET Framework 4.6 및 이상 버전에 포함 된 새로운 64 비트 JIT 컴파일러를 사용 합니다. |  
| 1     | 공용 언어 런타임에서 이전 64 비트 JIT 컴파일러를 사용합니다.                                                     |  
  
### <a name="child-elements"></a>자식 요소

없음
  
### <a name="parent-elements"></a>부모 요소  
  
| 요소         | 설명                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | 공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다. |  
| `runtime`       | 런타임 초기화 옵션에 대한 정보를 포함합니다.                                                        |  
  
## <a name="remarks"></a>설명  

.NET Framework 4.6부터 공용 언어 런타임에서 사용 하 여 새 64 비트 컴파일러를 jit (JUST-IN-TIME) 컴파일에 기본적으로. 일부 경우에는 64 비트 JIT 컴파일러의 이전 버전에서 JIT-컴파일된 응용 프로그램 코드 로부터 동작의 차이에 따라서 수 있습니다. 설정 하 여 합니다 `enabled` 특성을 `<useLegacyJit>` 요소를 `1`, 새로운 64 비트 JIT 컴파일러를 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 하 여 앱을 컴파일할 수 있습니다.  
  
> [!NOTE]
> `<useLegacyJit>` 요소 64 비트 JIT 컴파일의 경우에 영향을 줍니다. 32 비트 JIT 컴파일러를 사용 하 여 컴파일 영향을 받지 않습니다.  
  
구성 파일 설정을 사용 하는 대신 다른 두 가지 방법으로 레거시 64 비트 JIT 컴파일러를 사용할 수 있습니다.  
  
- 환경 변수를 설정합니다.

  설정 된 `COMPLUS_useLegacyJit` 환경 변수를 하나 `0` (새로운 64 비트 JIT 컴파일러 사용) 또는 `1` (이전 64 비트 JIT 컴파일러 사용):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  환경 변수가 *전역 범위*, 즉, 영향을 주는 모든 응용 프로그램 컴퓨터에서 실행 됩니다. 경우 설정 재정의할 수 있습니다 응용 프로그램 구성 파일 설정에 따라 합니다. 환경 변수 이름이 대/소문자 구분 아닙니다.
  
- 레지스트리 키 추가

  추가 하 여 레거시 64 비트 JIT 컴파일러를 사용할 수는 `REG_DWORD` 값 중 하나는 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 또는 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 레지스트리 키. 값 이름은 `useLegacyJit`합니다. 값이 0 이면 새로운 컴파일러 사용 됩니다. 값이 1 이면 레거시 64 비트 JIT 컴파일러를 사용 합니다. 레지스트리 값 이름이 대/소문자 구분 합니다.
  
  값을 추가 합니다 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 키 컴퓨터에서 실행 되는 모든 앱에 영향을 줍니다. 값을 추가 합니다 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 키 현재 사용자가 실행 되는 모든 앱에 영향을 줍니다. 컴퓨터를 여러 사용자 계정으로 구성 된 경우 현재 사용자가 실행 하는 앱만 영향을 받습니다를 값으로 다른 사용자에 대 한 레지스트리 키를 추가 하지 않으면. 추가 된 `<useLegacyJit>` 요소 구성 파일에 있는 경우 레지스트리 설정을 재정의 합니다.  
  
## <a name="example"></a>예제  

다음 구성 파일 새 64 비트 JIT 컴파일러를 사용 하 여 컴파일 사용 하지 않도록 설정 하 고 대신 레거시 64 비트 JIT 컴파일러를 사용 합니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [\<런타임 > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
- [완화: 새로운 64 비트 JIT 컴파일러](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
