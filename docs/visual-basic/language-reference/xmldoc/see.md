---
title: <see>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c26e818276eb4654fec77230372a0ae090952961
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474841"
---
# <a name="see-visual-basic"></a><span data-ttu-id="22331-102">\<참조 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22331-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="22331-103">다른 멤버에 대 한 링크를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22331-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22331-104">구문</span><span class="sxs-lookup"><span data-stu-id="22331-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="22331-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22331-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="22331-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="22331-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="22331-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22331-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="22331-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22331-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22331-109">설명</span><span class="sxs-lookup"><span data-stu-id="22331-109">Remarks</span></span>  
 <span data-ttu-id="22331-110">사용 된 `<see>` 텍스트 내에서 링크를 지정 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="22331-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="22331-111">사용 하 여 [ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) "참고 항목" 섹션에 표시 하려는 텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22331-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="22331-112">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="22331-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22331-113">예제</span><span class="sxs-lookup"><span data-stu-id="22331-113">Example</span></span>  
 <span data-ttu-id="22331-114">이 예제에서는 합니다 `<see>` 태그를 `UpdateRecord` 주의 섹션을 참조는 `DoesRecordExist` 메서드.</span><span class="sxs-lookup"><span data-stu-id="22331-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="22331-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="22331-115">See also</span></span>
- [<span data-ttu-id="22331-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="22331-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
