---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 71b00b669804e644d1171480192b9d55455bdf53
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352273"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="6e39b-101">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e39b-101">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="6e39b-102">Specifies a required permission for the member.</span><span class="sxs-lookup"><span data-stu-id="6e39b-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e39b-103">구문</span><span class="sxs-lookup"><span data-stu-id="6e39b-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e39b-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e39b-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="6e39b-105">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="6e39b-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="6e39b-106">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e39b-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="6e39b-107">Enclose `member` in quotation marks (" ").</span><span class="sxs-lookup"><span data-stu-id="6e39b-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="6e39b-108">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="6e39b-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e39b-109">주의</span><span class="sxs-lookup"><span data-stu-id="6e39b-109">Remarks</span></span>  
 <span data-ttu-id="6e39b-110">Use the `<permission>` tag to document the access of a member.</span><span class="sxs-lookup"><span data-stu-id="6e39b-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="6e39b-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span><span class="sxs-lookup"><span data-stu-id="6e39b-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="6e39b-112">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6e39b-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e39b-113">예제</span><span class="sxs-lookup"><span data-stu-id="6e39b-113">Example</span></span>  
 <span data-ttu-id="6e39b-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span><span class="sxs-lookup"><span data-stu-id="6e39b-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="6e39b-115">참조</span><span class="sxs-lookup"><span data-stu-id="6e39b-115">See also</span></span>

- [<span data-ttu-id="6e39b-116">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="6e39b-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
