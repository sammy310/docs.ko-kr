---
title: XML 데이터 형식 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: 108cfbf1ee8ff3d6fbe088d6dd14d0354750cb0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701499"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="ba18d-102">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="ba18d-102">Conversion of XML Data Types</span></span>

<span data-ttu-id="ba18d-103">**XmlConvert** 클래스에 있는 대부분의 메서드는 문자열과 강력한 형식의 서식 간에 데이터를 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly typed formats.</span></span> <span data-ttu-id="ba18d-104">메서드는 로캘과 무관합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-104">Methods are locale independent.</span></span> <span data-ttu-id="ba18d-105">즉, 변환을 수행하는 경우 메서드는 로캘 설정을 고려하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="ba18d-106">문자열을 형식으로 읽기</span><span class="sxs-lookup"><span data-stu-id="ba18d-106">Reading String as types</span></span>  

 <span data-ttu-id="ba18d-107">다음 샘플에서는 문자열을 읽고 이 문자열을 **DateTime** 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="ba18d-108">다음과 같은 XML 입력을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="ba18d-109">**입력**</span><span class="sxs-lookup"><span data-stu-id="ba18d-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="ba18d-110">이 코드는 다음과 같이 문자열을 **DateTime** 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="ba18d-111">문자열을 형식으로 쓰기</span><span class="sxs-lookup"><span data-stu-id="ba18d-111">Writing Strings as types</span></span>  

 <span data-ttu-id="ba18d-112">다음 샘플에서는 **Int32** 를 읽고 문자열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="ba18d-113">다음과 같은 XML 입력을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="ba18d-114">**입력**</span><span class="sxs-lookup"><span data-stu-id="ba18d-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="ba18d-115">이 코드는 다음과 같이 **Int32** 를 **String** 으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba18d-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba18d-116">참조</span><span class="sxs-lookup"><span data-stu-id="ba18d-116">See also</span></span>

- [<span data-ttu-id="ba18d-117">문자열을 .NET Framework 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="ba18d-117">Converting Strings to .NET Framework Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
- [<span data-ttu-id="ba18d-118">.NET Framework 형식을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="ba18d-118">Converting .NET Framework Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
