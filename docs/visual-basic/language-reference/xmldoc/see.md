---
title: <see>(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524663"
---
# <a name="see-visual-basic"></a><span data-ttu-id="0c8d1-102">\<see > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c8d1-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="0c8d1-103">다른 멤버에 대 한 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c8d1-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c8d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0c8d1-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="0c8d1-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0c8d1-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="0c8d1-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c8d1-109">주의</span><span class="sxs-lookup"><span data-stu-id="0c8d1-109">Remarks</span></span>  
 <span data-ttu-id="0c8d1-110">@No__t_0 태그를 사용 하 여 텍스트 내에서 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="0c8d1-111">[@No__t_1seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) 를 사용 하 여 "참고 항목" 섹션에 표시할 텍스트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="0c8d1-112">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c8d1-113">예제</span><span class="sxs-lookup"><span data-stu-id="0c8d1-113">Example</span></span>  
 <span data-ttu-id="0c8d1-114">이 예제에서는 `UpdateRecord` 설명 섹션의 `<see>` 태그를 사용 하 여 `DoesRecordExist` 메서드를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c8d1-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0c8d1-115">참조</span><span class="sxs-lookup"><span data-stu-id="0c8d1-115">See also</span></span>

- [<span data-ttu-id="0c8d1-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="0c8d1-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
