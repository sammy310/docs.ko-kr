---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 51eaaef2ddb88afbb52ab58b85ed1a58ba251c1e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866445"
---
# <a name="see-visual-basic"></a><span data-ttu-id="93daf-101">\<see>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93daf-101">\<see> (Visual Basic)</span></span>

<span data-ttu-id="93daf-102">다른 멤버에 대 한 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93daf-103">구문</span><span class="sxs-lookup"><span data-stu-id="93daf-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="93daf-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93daf-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="93daf-105">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="93daf-106">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="93daf-107">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93daf-108">설명</span><span class="sxs-lookup"><span data-stu-id="93daf-108">Remarks</span></span>  

 <span data-ttu-id="93daf-109">태그를 사용 `<see>` 하 여 텍스트 내에서 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="93daf-110">[\<seealso>](seealso.md)"참고 항목" 섹션에 표시할 텍스트를 나타내는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="93daf-111">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93daf-112">예제</span><span class="sxs-lookup"><span data-stu-id="93daf-112">Example</span></span>  

 <span data-ttu-id="93daf-113">이 예제에서는 `<see>` 설명 섹션의 태그를 사용 하 여 `UpdateRecord` 메서드를 참조 `DoesRecordExist` 합니다.</span><span class="sxs-lookup"><span data-stu-id="93daf-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="93daf-114">참조</span><span class="sxs-lookup"><span data-stu-id="93daf-114">See also</span></span>

- [<span data-ttu-id="93daf-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="93daf-115">XML Comment Tags</span></span>](index.md)
