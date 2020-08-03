---
title: '완화: 응용 프로그램 도메인 간 개체의 deserialization'
description: 여러 앱 도메인 간에 논리 호출 컨텍스트의 개체를 역직렬화하려고 시도하면 예외가 throw되는 문제를 진단하고 완화하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
ms.openlocfilehash: 20ea0f2f0b49000b7d1993adb583a803d9f5be6c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475244"
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a>완화: 애플리케이션 도메인 간 개체의 deserialization
경우에 따라 앱이 다양한 애플리케이션을 기반으로 하여 두 개 이상의 애플리케이션 도메인을 사용하면 여러 애플리케이션 도메인 간에 논리 호출 컨텍스트의 개체를 역직렬화하려는 시도로 인해 예외가 throw됩니다.  
  
## <a name="diagnosing-the-issue"></a>문제 진단  
 다음 조건의 순서대로 문제가 발생합니다.  
  
1. 앱이 다양한 애플리케이션을 기반으로 하여 두 개 이상의 애플리케이션 도메인을 사용합니다.  
  
2. 일부 형식은 <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> 또는 <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType>와 같은 메서드를 호출하여 <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType>에 명시적으로 추가됩니다. 이러한 형식은 serializable로 표시되지 않고 전역 어셈블리 캐시에 저장되지 않습니다.  
  
3. 나중에 기본이 아닌 응용 프로그램 도메인에서 실행되는 코드가 구성 파일에서 값을 읽거나 XML을 사용하여 개체를 역직렬화하려고 시도합니다.  
  
4. 구성 파일에서 읽거나 개체를 역직렬화하기 위해 <xref:System.Xml.XmlReader> 개체는 구성 시스템에 액세스하려고 시도합니다.  
  
5. 구성 시스템이 아직 초기화되지 않은 경우, 초기화를 완료해야 합니다. 즉, 런타임은 실제로 다음과 같이 구성 시스템에 대한 안정적인 경로를 만들어야 합니다.  
  
    1. 기본이 아닌 응용 프로그램 도메인의 증명 정보를 찾습니다.  
  
    2. 기본 응용 프로그램 도메인을 기반으로 하여 기본이 아닌 응용 프로그램 도메인의 증명 정보를 계산하려고 합니다.  
  
    3. 기본 응용 프로그램 도메인의 증명 정보를 가져오기 위한 호출은 기본이 아닌 응용 프로그램 도메인에서 기본 응용 프로그램 도메인으로 응용 프로그램 간 도메인 호출을 트리거합니다.  
  
    4. .NET Framework에서 응용 프로그램 간 도메인 계약의 일부로서 논리 호출 컨텍스트의 내용 또한 응용 프로그램 도메인 경계를 넘어 마샬링해야 합니다.  
  
6. 기본 응용 프로그램 도메인에서 논리 호출 컨텍스트에 있는 형식을 확인할 수 없으므로 예외가 throw됩니다.  
  
## <a name="mitigation"></a>완화  
 이 문제를 해결하려면 다음을 수행합니다.  
  
1. 예외가 throw될 때 호출 스택에서 `get_Evidence`에 대한 호출을 찾습니다. 이 예외는 <xref:System.IO.FileNotFoundException> 및 <xref:System.Runtime.Serialization.SerializationException>을 포함한 예외의 큰 하위 집합 중 하나일 수 있습니다.  
  
2. 응용 프로그램에서 개체가 논리 호출 컨텍스트에 추가되지 않은 위치를 찾아 다음 코드를 추가합니다.  
  
    ```csharp
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```
  
## <a name="see-also"></a>참조

- [애플리케이션 호환성](application-compatibility.md)
