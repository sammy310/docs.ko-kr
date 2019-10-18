---
title: <exception>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 16ffb4f6b57dabb3650376c913a7d7608a00646d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523927"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="f0c1f-102">\<exception > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0c1f-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="f0c1f-103">Throw 할 수 있는 예외를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c1f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0c1f-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0c1f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0c1f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="f0c1f-106">현재 컴파일 환경에서 사용할 수 있는 예외에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="f0c1f-107">컴파일러는 지정된 예외가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="f0c1f-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f0c1f-109">설명.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0c1f-110">주의</span><span class="sxs-lookup"><span data-stu-id="f0c1f-110">Remarks</span></span>  
 <span data-ttu-id="f0c1f-111">@No__t_0 태그를 사용 하 여 throw 할 수 있는 예외를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="f0c1f-112">이 태그는 메서드 정의에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="f0c1f-113">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c1f-114">예제</span><span class="sxs-lookup"><span data-stu-id="f0c1f-114">Example</span></span>  
 <span data-ttu-id="f0c1f-115">이 예제에서는 `<exception>` 태그를 사용 하 여 `IntDivide` 함수가 throw 할 수 있는 예외를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c1f-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c1f-116">참조</span><span class="sxs-lookup"><span data-stu-id="f0c1f-116">See also</span></span>

- [<span data-ttu-id="f0c1f-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="f0c1f-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
