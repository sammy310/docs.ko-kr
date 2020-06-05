---
title: XML 주석 예외에는 'cref' 특성이 있어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406510"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="b6480-102">XML 주석 예외에는 'cref' 특성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6480-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="b6480-103">\<exception>태그는 메서드에 의해 throw 될 수 있는 예외를 문서화 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6480-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="b6480-104">Required `cref` 특성은 문서 생성기에 의해 확인 되는 멤버의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6480-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="b6480-105">멤버가 있으면 설명서 파일의 정식 요소 이름으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6480-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="b6480-106">**오류 ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="b6480-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b6480-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b6480-107">To correct this error</span></span>

<span data-ttu-id="b6480-108">다음과 `cref` 같이 예외에 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6480-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="b6480-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6480-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="b6480-110">방법: XML 설명서 만들기</span><span class="sxs-lookup"><span data-stu-id="b6480-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="b6480-111">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="b6480-111">XML Comment Tags</span></span>](../xmldoc/index.md)
