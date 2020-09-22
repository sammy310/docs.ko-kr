---
title: XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 861677636f9a73015b26efec30df728d07fbdf72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870210"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="3ec50-102">XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec50-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="3ec50-103">XML 리터럴 및 XML 속성은 ASP.NET 내의 포함 코드에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec50-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="3ec50-104">XML 기능을 사용 하려면 코드를 코드 숨김으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec50-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="3ec50-105">XML 리터럴 또는 XML 축 속성은 ASP.NET 파일의 포함 코드 () 내에 정의 됩니다 `<%= =>` .</span><span class="sxs-lookup"><span data-stu-id="3ec50-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="3ec50-106">**오류 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="3ec50-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3ec50-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3ec50-107">To correct this error</span></span>  
  
- <span data-ttu-id="3ec50-108">XML 리터럴 또는 XML 축 속성을 포함 하는 코드를 ASP.NET 코드 숨김으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec50-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec50-109">참조</span><span class="sxs-lookup"><span data-stu-id="3ec50-109">See also</span></span>

- [<span data-ttu-id="3ec50-110">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="3ec50-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="3ec50-111">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="3ec50-111">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="3ec50-112">XML</span><span class="sxs-lookup"><span data-stu-id="3ec50-112">XML</span></span>](../../programming-guide/language-features/xml/index.md)
