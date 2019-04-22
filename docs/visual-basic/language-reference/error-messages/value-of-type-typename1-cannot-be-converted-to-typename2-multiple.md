---
title: "'<typename1>' 형식의 값을 '<typename2>'(으)로 변환할 수 없습니다.(여러 파일 참조)"
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 58b334eb5e6db443bcfaba72729d59cb1d798e70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833531"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="f58ed-102">형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >' (여러 파일 참조)</span><span class="sxs-lookup"><span data-stu-id="f58ed-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="f58ed-103">형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="f58ed-104">형식 불일치에 대 한 파일 참조가 섞여 때문일 수 있습니다 '\<filepath1 >' 프로젝트에서 '\<projectname1 >'에 대 한 파일 참조를 사용 하 여 '\<filepath2 >' 프로젝트에서 '\<projectname2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="f58ed-105">두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.</span><span class="sxs-lookup"><span data-stu-id="f58ed-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="f58ed-106">프로젝트의 어셈블리에 둘 이상의 파일 참조는 있는 경우에서 컴파일러는 형식 간에 변환할 수는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="f58ed-107">각 파일 참조 (일반적으로 DLL 파일) 프로젝트의 출력 파일 이름과 파일 경로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="f58ed-108">컴파일러는 동일한 소스에서 출력 파일 지거나 동일한 어셈블리의 동일한 버전을 표시 하는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="f58ed-109">따라서 다른 참조의 형식은 동일한 형식 또는 다른 하나의 변환할 수는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="f58ed-110">참조 된 어셈블리는 동일한 어셈블리 id를 알고 있는 경우 단일 파일 참조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="f58ed-111">*어셈블리 ID* 에는 어셈블리 이름, 버전, 공개 키(있는 경우) 및 문화권이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="f58ed-112">이 정보는 어셈블리를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="f58ed-113">**오류 ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="f58ed-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f58ed-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f58ed-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f58ed-115">참조 된 어셈블리에서 동일한 어셈블리 id에 있는 경우 제거 하거나 단일 파일 참조만 되도록 파일 참조 중 하나를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="f58ed-116">참조 된 어셈블리는 동일한 어셈블리 id에 없는 경우 형식에서 다른 형식으로 변환 하려고 하지 않도록 코드를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f58ed-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58ed-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f58ed-117">See also</span></span>

- [<span data-ttu-id="f58ed-118">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="f58ed-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="f58ed-119">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="f58ed-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
