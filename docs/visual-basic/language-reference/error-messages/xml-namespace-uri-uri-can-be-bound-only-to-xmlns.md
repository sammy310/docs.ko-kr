---
title: XML 네임스페이스 URI '<uri>'는 'xmlns'에만 바인딩할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163248"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a><span data-ttu-id="24726-102">BC31183: XML 네임 스페이스 URI `http://www.w3.org/XML/1998/namespace` 는 ' xmlns '에만 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24726-102">BC31183: XML namespace URI `http://www.w3.org/XML/1998/namespace`; can be bound only to 'xmlns'</span></span>

<span data-ttu-id="24726-103">URI는 `http://www.w3.org/XML/1998/namespace` XML 네임 스페이스 선언에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24726-103">The URI `http://www.w3.org/XML/1998/namespace` is used in an XML namespace declaration.</span></span> <span data-ttu-id="24726-104">이 URI는 예약 된 네임 스페이스 이며 XML 네임 스페이스 선언에 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24726-104">This URI is a reserved namespace and cannot be included in an XML namespace declaration.</span></span>

 <span data-ttu-id="24726-105">**오류 ID:** BC31183</span><span class="sxs-lookup"><span data-stu-id="24726-105">**Error ID:** BC31183</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="24726-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="24726-106">To correct this error</span></span>

<span data-ttu-id="24726-107">XML 네임 스페이스 선언을 제거 하거나 URI를 `http://www.w3.org/XML/1998/namespace` 올바른 네임 스페이스 uri로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="24726-107">Remove the XML namespace declaration or replace the URI `http://www.w3.org/XML/1998/namespace` with a valid namespace URI.</span></span>

## <a name="see-also"></a><span data-ttu-id="24726-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24726-108">See also</span></span>

- [<span data-ttu-id="24726-109">Imports 문(XML 네임스페이스)</span><span class="sxs-lookup"><span data-stu-id="24726-109">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="24726-110">XML 리터럴</span><span class="sxs-lookup"><span data-stu-id="24726-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="24726-111">XML</span><span class="sxs-lookup"><span data-stu-id="24726-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
