---
title: <UseRandomizedStringHashAlgorithm> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153779"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<사용임의적 스트링해시 알고리즘> 요소
공통 언어 런타임이 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산하는지 여부를 결정합니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<사용임의적 스트링해시 알고리즘>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 문자열에 대한 해시 코드가 응용 프로그램 도메인별로 계산되는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|Description|  
|-----------|-----------------|  
|`0`|공통 언어 런타임은 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산하지 않습니다. 단일 알고리즘은 문자열 해시 코드를 계산하는 데 사용됩니다. 이것이 기본값입니다.|  
|`1`|공통 언어 런타임은 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산합니다. 서로 다른 응용 프로그램 도메인과 다른 프로세스의 동일한 문자열에는 서로 다른 해시 코드가 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 클래스와 <xref:System.StringComparer> 메서드는 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 응용 프로그램 도메인 간에 일관된 해시 코드를 생성하는 단일 해시 알고리즘을 사용합니다. 이는 `enabled` `<UseRandomizedStringHashAlgorithm>` 요소의 특성을 에 설정하는 `0`것과 같습니다. .NET Framework 4에 사용되는 해싱 알고리즘입니다.  
  
 클래스와 <xref:System.StringComparer> <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드는 응용 프로그램 도메인별로 해시 코드를 계산하는 다른 해시 알고리즘을 사용할 수도 있습니다. 따라서 해당 문자열에 대한 해시 코드는 응용 프로그램 도메인마다 다릅니다. 이 기능은 옵트인 기능입니다. 이를 활용하려면 요소의 특성을 `enabled` `<UseRandomizedStringHashAlgorithm>` `1`로 설정해야 합니다.  
  
 해시 테이블의 문자열 조회는 일반적으로 O(1) 작업입니다. 그러나 많은 수의 충돌이 발생하면 조회가<sup>O(n2)</sup>작업이 될 수 있습니다. `<UseRandomizedStringHashAlgorithm>` 구성 요소를 사용하여 응용 프로그램 도메인당 임의의 해싱 알고리즘을 생성할 수 있으며, 특히 해시 코드가 계산되는 키가 사용자가 입력한 데이터를 기반으로 하는 경우 잠재적충돌 횟수를 제한할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 "이 문자열은 문자열입니다"라는 값을 포함하는 전용 문자열 상수를 `DisplayString` `s`포함하는 클래스를 정의합니다. 메서드를 실행하는 애플리케이션 도메인의 이름과 함께 문자열 값 및 해시 코드를 표시하는 `ShowStringHashCode` 메서드도 포함합니다.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 구성 파일을 지정하지 않고 이 예제를 실행할 경우 다음과 유사한 출력이 표시됩니다. 문자열의 해시 코드는 두 애플리케이션 도메인에서 동일합니다.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 하지만 샘플 디렉터리에 다음의 구성을 추가하고 샘플을 실행하는 경우 동일 문자열의 해시 코드는 애플리케이션 도메인에 의해 달라집니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 구성 파일이 있는 경우 예제는 다음과 같은 출력을 표시합니다.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
