---
description: 'BC31200: XML 리터럴 및 XML 속성이 ASP.NET 내의 포함 코드에서 지원 되지 않음에 대해 자세히 알아보세요.'
title: XML 리터럴 및 XML 속성은 ASP.NET의 포함 코드에서 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 0a5328676ee38a56334b77f665a464daa586ce3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701406"
---
# <a name="bc31200-xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="1a327-103">BC31200: ASP.NET 내의 포함 코드에서는 XML 리터럴 및 XML 속성이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a327-103">BC31200: XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>

<span data-ttu-id="1a327-104">XML 리터럴 및 XML 속성은 ASP.NET 내의 포함 코드에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a327-104">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="1a327-105">XML 기능을 사용 하려면 코드를 코드 숨김으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a327-105">To use XML features, move the code to code-behind.</span></span>

 <span data-ttu-id="1a327-106">XML 리터럴 또는 XML 축 속성은 ASP.NET 파일의 포함 코드 () 내에 정의 됩니다 `<%= =>` .</span><span class="sxs-lookup"><span data-stu-id="1a327-106">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>

 <span data-ttu-id="1a327-107">**오류 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="1a327-107">**Error ID:** BC31200</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1a327-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1a327-108">To correct this error</span></span>

- <span data-ttu-id="1a327-109">XML 리터럴 또는 XML 축 속성을 포함 하는 코드를 ASP.NET 코드 숨김으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a327-109">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a327-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a327-110">See also</span></span>

- [<span data-ttu-id="1a327-111">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="1a327-111">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="1a327-112">XML 축 속성</span><span class="sxs-lookup"><span data-stu-id="1a327-112">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="1a327-113">XML</span><span class="sxs-lookup"><span data-stu-id="1a327-113">XML</span></span>](../../programming-guide/language-features/xml/index.md)
