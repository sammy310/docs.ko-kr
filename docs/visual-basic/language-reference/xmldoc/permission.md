---
description: 다음에 대해 자세히 알아보세요. <permission> (Visual Basic)
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7a227e97051002c834c96297d3028f08e3ed07ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700262"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="1eb71-103">\<permission>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eb71-103">\<permission> (Visual Basic)</span></span>

<span data-ttu-id="1eb71-104">멤버에 필요한 사용 권한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-104">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb71-105">구문</span><span class="sxs-lookup"><span data-stu-id="1eb71-105">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb71-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1eb71-106">Parameters</span></span>  

 `member`  
 <span data-ttu-id="1eb71-107">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-107">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="1eb71-108">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-108">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="1eb71-109">`member`큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-109">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="1eb71-110">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eb71-111">설명</span><span class="sxs-lookup"><span data-stu-id="1eb71-111">Remarks</span></span>  

 <span data-ttu-id="1eb71-112">태그를 사용 `<permission>` 하 여 멤버에 대 한 액세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-112">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="1eb71-113">클래스를 사용 <xref:System.Security.PermissionSet> 하 여 멤버에 대 한 액세스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-113">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="1eb71-114">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1eb71-114">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eb71-115">예제</span><span class="sxs-lookup"><span data-stu-id="1eb71-115">Example</span></span>  

 <span data-ttu-id="1eb71-116">이 예제에서는 태그를 사용 하 여 `<permission>` <xref:System.Security.Permissions.FileIOPermission> 이 메서드에 필요 함을 설명 합니다 `ReadFile` .</span><span class="sxs-lookup"><span data-stu-id="1eb71-116">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="1eb71-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eb71-117">See also</span></span>

- [<span data-ttu-id="1eb71-118">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="1eb71-118">XML Comment Tags</span></span>](index.md)
