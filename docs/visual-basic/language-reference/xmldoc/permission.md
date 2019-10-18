---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 904d573514bf35b773d47321b7fd3b6a86e90262
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524693"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="a78f8-102">\<permission > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a78f8-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="a78f8-103">멤버에 필요한 사용 권한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a78f8-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a78f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a78f8-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="a78f8-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="a78f8-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="a78f8-108">@No__t_0를 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="a78f8-109">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a78f8-110">주의</span><span class="sxs-lookup"><span data-stu-id="a78f8-110">Remarks</span></span>  
 <span data-ttu-id="a78f8-111">@No__t_0 태그를 사용 하 여 멤버에 대 한 액세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="a78f8-112">@No__t_0 클래스를 사용 하 여 멤버에 대 한 액세스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="a78f8-113">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a78f8-114">예제</span><span class="sxs-lookup"><span data-stu-id="a78f8-114">Example</span></span>  
 <span data-ttu-id="a78f8-115">이 예제에서는 `<permission>` 태그를 사용 하 여 <xref:System.Security.Permissions.FileIOPermission> `ReadFile` 메서드에 필요 함을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a78f8-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="a78f8-116">참조</span><span class="sxs-lookup"><span data-stu-id="a78f8-116">See also</span></span>

- [<span data-ttu-id="a78f8-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="a78f8-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
