---
title: <permission> - C# 프로그래밍 가이드
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 67e9d398d1bb43d480f8ca56733106e0f0a22731
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696573"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="22012-102">\<permission>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="22012-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="22012-103">구문</span><span class="sxs-lookup"><span data-stu-id="22012-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="22012-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22012-104">Parameters</span></span>  
 <span data-ttu-id="22012-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="22012-105">cref = " `member`"</span></span>  
 <span data-ttu-id="22012-106">현재 컴파일 환경에서 호출할 수 있는 멤버 또는 필드에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="22012-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="22012-107">컴파일러는 지정된 코드 요소가 있으며 `member`를 출력 XML의 정식 요소 이름으로 변환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22012-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="22012-108">*member*는 큰따옴표(“ ”)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22012-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="22012-109">제네릭 형식에 대한 cref 참조를 만드는 방법에 대한 자세한 내용은 [\<see>](./see.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22012-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="22012-110">멤버 액세스 권한에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="22012-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22012-111">설명</span><span class="sxs-lookup"><span data-stu-id="22012-111">Remarks</span></span>  
 <span data-ttu-id="22012-112">\<permission> 태그를 사용하면 멤버 액세스 권한을 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22012-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="22012-113"><xref:System.Security.PermissionSet> 클래스를 사용하면 멤버 액세스 권한을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22012-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="22012-114">[-doc](../../language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="22012-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22012-115">예제</span><span class="sxs-lookup"><span data-stu-id="22012-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="22012-116">참조</span><span class="sxs-lookup"><span data-stu-id="22012-116">See also</span></span>

- [<span data-ttu-id="22012-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="22012-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="22012-118">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="22012-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
