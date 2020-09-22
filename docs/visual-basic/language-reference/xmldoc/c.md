---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 969df339eb766d2edb444ab5626af4e69accddba
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871706"
---
# <a name="c-visual-basic"></a><span data-ttu-id="40299-101">\<c>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40299-101">\<c> (Visual Basic)</span></span>

<span data-ttu-id="40299-102">설명의 텍스트가 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40299-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40299-103">구문</span><span class="sxs-lookup"><span data-stu-id="40299-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="40299-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40299-104">Parameters</span></span>  
  
|<span data-ttu-id="40299-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40299-105">Parameter</span></span>|<span data-ttu-id="40299-106">Description</span><span class="sxs-lookup"><span data-stu-id="40299-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="40299-107">코드로 표시하려는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="40299-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40299-108">설명</span><span class="sxs-lookup"><span data-stu-id="40299-108">Remarks</span></span>  

 <span data-ttu-id="40299-109">`<c>` 태그를 사용하면 설명 내의 텍스트를 코드로 표시해야 함을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40299-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="40299-110">여러 줄을 코드로 지정하려면 [\<code>](code.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40299-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="40299-111">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="40299-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40299-112">예제</span><span class="sxs-lookup"><span data-stu-id="40299-112">Example</span></span>  

 <span data-ttu-id="40299-113">이 예제에서는 `<c>` 요약 섹션의 태그를 사용 하 여가 code 임을 표시 합니다 `Counter` .</span><span class="sxs-lookup"><span data-stu-id="40299-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="40299-114">참조</span><span class="sxs-lookup"><span data-stu-id="40299-114">See also</span></span>

- [<span data-ttu-id="40299-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="40299-115">XML Comment Tags</span></span>](index.md)
