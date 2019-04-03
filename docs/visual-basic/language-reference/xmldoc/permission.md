---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7333d4a4d051c157f6732224da0fffe4d7cd35ee
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827668"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="2a816-102">\<사용 권한 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a816-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="2a816-103">멤버에 대 한 필요한 사용 권한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a816-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a816-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a816-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a816-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="2a816-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2a816-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2a816-108">묶습니다 `member` 큰따옴표에서 ("").</span><span class="sxs-lookup"><span data-stu-id="2a816-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2a816-109">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a816-110">설명</span><span class="sxs-lookup"><span data-stu-id="2a816-110">Remarks</span></span>  
 <span data-ttu-id="2a816-111">사용 된 `<permission>` 멤버에 대 한 액세스를 문서화 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="2a816-112">사용 된 <xref:System.Security.PermissionSet> 멤버에 대 한 액세스를 지정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="2a816-113">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2a816-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a816-114">예제</span><span class="sxs-lookup"><span data-stu-id="2a816-114">Example</span></span>  
 <span data-ttu-id="2a816-115">이 예에서는 `<permission>` 태그를 설명 하는 <xref:System.Security.Permissions.FileIOPermission> 에 필요한는 `ReadFile` 메서드.</span><span class="sxs-lookup"><span data-stu-id="2a816-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="2a816-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a816-116">See also</span></span>

- [<span data-ttu-id="2a816-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="2a816-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
