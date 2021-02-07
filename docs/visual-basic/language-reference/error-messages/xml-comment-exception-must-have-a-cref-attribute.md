---
description: "자세한 정보: BC42319: XML 주석 예외에는 ' cref ' 특성이 있어야 합니다."
title: XML 주석 예외에는 'cref' 특성이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: e602a2973d95f70d5ab532e6be319a9575d239a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701458"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="6da16-103">BC42319: XML 주석 예외에는 ' cref ' 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da16-103">BC42319: XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="6da16-104">\<exception>태그는 메서드에 의해 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da16-104">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="6da16-105">Required `cref` 특성은 문서 생성기에 의해 확인 되는 멤버의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da16-105">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="6da16-106">멤버가 있으면 설명서 파일의 정식 요소 이름으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6da16-106">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="6da16-107">**오류 ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="6da16-107">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6da16-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6da16-108">To correct this error</span></span>

<span data-ttu-id="6da16-109">다음과 `cref` 같이 예외에 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6da16-109">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="6da16-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6da16-110">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="6da16-111">방법: XML 설명서 만들기</span><span class="sxs-lookup"><span data-stu-id="6da16-111">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="6da16-112">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="6da16-112">XML Comment Tags</span></span>](../xmldoc/index.md)
