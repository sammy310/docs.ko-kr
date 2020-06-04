---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400165"
---
# <a name="c-visual-basic"></a><span data-ttu-id="0f25c-101">\<c>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f25c-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="0f25c-102">설명의 텍스트가 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f25c-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f25c-103">구문</span><span class="sxs-lookup"><span data-stu-id="0f25c-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f25c-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f25c-104">Parameters</span></span>  
  
|<span data-ttu-id="0f25c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f25c-105">Parameter</span></span>|<span data-ttu-id="0f25c-106">Description</span><span class="sxs-lookup"><span data-stu-id="0f25c-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="0f25c-107">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="0f25c-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f25c-108">설명</span><span class="sxs-lookup"><span data-stu-id="0f25c-108">Remarks</span></span>  
 <span data-ttu-id="0f25c-109">`<c>`태그는 설명 내의 텍스트를 코드로 표시 하도록 지정 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f25c-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="0f25c-110">[\<code>](code.md)를 사용 하 여 여러 줄을 코드로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f25c-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="0f25c-111">[-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f25c-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f25c-112">예제</span><span class="sxs-lookup"><span data-stu-id="0f25c-112">Example</span></span>  
 <span data-ttu-id="0f25c-113">이 예제에서는 `<c>` 요약 섹션의 태그를 사용 하 여가 code 임을 표시 합니다 `Counter` .</span><span class="sxs-lookup"><span data-stu-id="0f25c-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0f25c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f25c-114">See also</span></span>

- [<span data-ttu-id="0f25c-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="0f25c-115">XML Comment Tags</span></span>](index.md)
