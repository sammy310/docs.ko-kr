---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0231ff748949874f4b477cac15d891d313b25f4f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524649"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="e79cb-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e79cb-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="e79cb-103">참고 항목 섹션에 표시 되는 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="e79cb-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e79cb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e79cb-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="e79cb-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="e79cb-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="e79cb-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e79cb-109">주의</span><span class="sxs-lookup"><span data-stu-id="e79cb-109">Remarks</span></span>  
 <span data-ttu-id="e79cb-110">@No__t_0 태그를 사용 하 여 참고 항목 섹션에 표시할 텍스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="e79cb-111">텍스트 내에서 링크를 지정하려면 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="e79cb-112">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e79cb-113">예제</span><span class="sxs-lookup"><span data-stu-id="e79cb-113">Example</span></span>  
 <span data-ttu-id="e79cb-114">이 예제에서는 `DoesRecordExist` 설명 섹션의 `<seealso>` 태그를 사용 하 여 `UpdateRecord` 메서드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e79cb-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e79cb-115">참조</span><span class="sxs-lookup"><span data-stu-id="e79cb-115">See also</span></span>

- [<span data-ttu-id="e79cb-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="e79cb-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
