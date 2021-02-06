---
description: '다음에 대 한 자세한 정보: <UseRandomizedStringHashAlgorithm> 요소'
title: <UseRandomizedStringHashAlgorithm> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: bb651fc9c9f6f3df448ed5ce19e81c1ae092838c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639980"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm> 요소

공용 언어 런타임이 응용 프로그램 도메인 별로 문자열의 해시 코드를 계산할지 여부를 결정 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 응용 프로그램 도메인 별로 문자열의 해시 코드를 계산할지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`0`|공용 언어 런타임은 응용 프로그램 도메인 별로 문자열의 해시 코드를 계산 하지 않습니다. 단일 알고리즘은 문자열 해시 코드를 계산 하는 데 사용 됩니다. 기본값입니다.|  
|`1`|공용 언어 런타임은 응용 프로그램 도메인 별로 문자열의 해시 코드를 계산 합니다. 서로 다른 응용 프로그램 도메인의 동일한 문자열과 다른 프로세스의 해시 코드는 서로 다릅니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  

 기본적으로 <xref:System.StringComparer> 클래스와 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 메서드는 응용 프로그램 도메인 간에 일관 된 해시 코드를 생성 하는 단일 해싱 알고리즘을 사용 합니다. 이는 요소의 특성을로 설정 하는 것과 같습니다 `enabled` `<UseRandomizedStringHashAlgorithm>` `0` . .NET Framework 4에서 사용 되는 해시 알고리즘입니다.  
  
 <xref:System.StringComparer>클래스와 메서드는 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> 응용 프로그램 도메인 별로 해시 코드를 계산 하는 다른 해싱 알고리즘을 사용할 수도 있습니다. 따라서 동일한 문자열의 해시 코드는 응용 프로그램 도메인에 따라 달라 집니다. 이 기능은 옵트인 (opt in) 기능입니다. 이를 활용 하려면 요소의 특성을로 설정 해야 합니다 `enabled` `<UseRandomizedStringHashAlgorithm>` `1` .  
  
 해시 테이블의 문자열 조회는 일반적으로 O (1) 연산입니다. 그러나 많은 수의 충돌이 발생 하면 조회는 O (n<sup>2</sup>) 작업이 될 수 있습니다. 구성 요소를 사용 하 여 `<UseRandomizedStringHashAlgorithm>` 응용 프로그램 도메인당 임의의 해싱 알고리즘을 생성할 수 있습니다 .이는 특히 해시 코드를 계산 하는 키가 사용자의 데이터 입력을 기반으로 하는 경우 잠재적 충돌 수를 제한 합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 `DisplayString` 전용 문자열 상수를 포함 하는 클래스를 정의 합니다 `s` . 해당 값은 "This is the string"입니다. 메서드를 실행하는 애플리케이션 도메인의 이름과 함께 문자열 값 및 해시 코드를 표시하는 `ShowStringHashCode` 메서드도 포함합니다.  
  
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
