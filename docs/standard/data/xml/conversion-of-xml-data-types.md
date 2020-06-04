---
title: XML 데이터 형식 변환
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: b6e6f2c4b28e9220727bf0fe1a958a7b69111571
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202156"
---
# <a name="conversion-of-xml-data-types"></a>XML 데이터 형식 변환
**XmlConvert** 클래스에 있는 대부분의 메서드는 문자열과 강력한 형식의 서식 간에 데이터를 변환하는 데 사용됩니다. 메서드는 로캘과 무관합니다. 즉, 변환을 수행하는 경우 메서드는 로캘 설정을 고려하지 않습니다.  
  
## <a name="reading-string-as-types"></a>문자열을 형식으로 읽기  
 다음 샘플에서는 문자열을 읽고 이 문자열을 **DateTime** 형식으로 변환합니다.  
  
 다음과 같은 XML 입력을 가정합니다.  
  
 **입력**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 이 코드는 다음과 같이 문자열을 **DateTime** 형식으로 변환합니다.  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>문자열을 형식으로 쓰기  
 다음 샘플에서는 **Int32**를 읽고 문자열로 변환합니다.  
  
 다음과 같은 XML 입력을 가정합니다.  
  
 **입력**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 이 코드는 다음과 같이 **Int32**를 **String**으로 변환합니다.  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>참조

- [문자열을 .NET Framework 데이터 형식으로 변환](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
- [.NET Framework 형식을 문자열로 변환](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
