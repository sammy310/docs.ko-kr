---
title: XML 엔터티 참조는 지원되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31180
- bc31180
helpviewer_keywords:
- BC31180
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
ms.openlocfilehash: 37e72dbd6de61a50b4192a0151db40cb4be49d1c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163274"
---
# <a name="bc31180-xml-entity-references-are-not-supported"></a><span data-ttu-id="89ec2-102">BC31180: XML 엔터티 참조는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89ec2-102">BC31180: XML entity references are not supported</span></span>

<span data-ttu-id="89ec2-103">`©`Xml 1.0 사양에 정의 되지 않은 엔터티 참조 (예:)는 xml 리터럴의 값으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89ec2-103">An entity reference (for example, `©`) that is not defined in the XML 1.0 specification is included as a value for an XML literal.</span></span> <span data-ttu-id="89ec2-104">Xml 리터럴에서는,, `&` `"` `<` , `>` 및 `'` xml 엔터티 참조만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89ec2-104">Only `&`, `"`, `<`, `>`, and `'` XML entity references are supported in XML literals.</span></span>

 <span data-ttu-id="89ec2-105">**오류 ID:** BC31180</span><span class="sxs-lookup"><span data-stu-id="89ec2-105">**Error ID:** BC31180</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="89ec2-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="89ec2-106">To correct this error</span></span>

- <span data-ttu-id="89ec2-107">지원 되지 않는 엔터티 참조를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ec2-107">Remove the unsupported entity reference.</span></span>

## <a name="see-also"></a><span data-ttu-id="89ec2-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89ec2-108">See also</span></span>

- [<span data-ttu-id="89ec2-109">XML 리터럴 및 XML 1.0 사양</span><span class="sxs-lookup"><span data-stu-id="89ec2-109">XML Literals and the XML 1.0 Specification</span></span>](../../programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)
- [<span data-ttu-id="89ec2-110">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="89ec2-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="89ec2-111">XML</span><span class="sxs-lookup"><span data-stu-id="89ec2-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
