---
description: '자세한 정보: <see> (Visual Basic)'
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 46dd67710f83d6c4549ddfeb6b7bbc1503b7aa1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640344"
---
# <a name="see-visual-basic"></a><span data-ttu-id="caae2-102">\<see>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caae2-102">\<see> (Visual Basic)</span></span>

<span data-ttu-id="caae2-103">다른 멤버에 대 한 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caae2-104">구문</span><span class="sxs-lookup"><span data-stu-id="caae2-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="caae2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="caae2-105">Parameters</span></span>  

 `member`  
 <span data-ttu-id="caae2-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="caae2-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 요소 이름에 전달하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="caae2-108">`member`는 큰따옴표(" ")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caae2-109">설명</span><span class="sxs-lookup"><span data-stu-id="caae2-109">Remarks</span></span>  

 <span data-ttu-id="caae2-110">태그를 사용 `<see>` 하 여 텍스트 내에서 링크를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="caae2-111">[\<seealso>](seealso.md)"참고 항목" 섹션에 표시할 텍스트를 나타내는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-111">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="caae2-112">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caae2-113">예제</span><span class="sxs-lookup"><span data-stu-id="caae2-113">Example</span></span>  

 <span data-ttu-id="caae2-114">이 예제에서는 `<see>` 설명 섹션의 태그를 사용 하 여 `UpdateRecord` 메서드를 참조 `DoesRecordExist` 합니다.</span><span class="sxs-lookup"><span data-stu-id="caae2-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="caae2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="caae2-115">See also</span></span>

- [<span data-ttu-id="caae2-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="caae2-116">XML Comment Tags</span></span>](index.md)
