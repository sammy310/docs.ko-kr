---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352225"
---
# <a name="see-visual-basic"></a><span data-ttu-id="ad2d7-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad2d7-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="ad2d7-102">Specifies a link to another member.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad2d7-103">구문</span><span class="sxs-lookup"><span data-stu-id="ad2d7-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad2d7-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad2d7-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="ad2d7-105">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ad2d7-106">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ad2d7-107">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad2d7-108">주의</span><span class="sxs-lookup"><span data-stu-id="ad2d7-108">Remarks</span></span>  
 <span data-ttu-id="ad2d7-109">Use the `<see>` tag to specify a link from within text.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="ad2d7-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="ad2d7-111">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad2d7-112">예제</span><span class="sxs-lookup"><span data-stu-id="ad2d7-112">Example</span></span>  
 <span data-ttu-id="ad2d7-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span><span class="sxs-lookup"><span data-stu-id="ad2d7-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ad2d7-114">참조</span><span class="sxs-lookup"><span data-stu-id="ad2d7-114">See also</span></span>

- [<span data-ttu-id="ad2d7-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="ad2d7-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
