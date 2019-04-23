---
title: '방법: (Visual Basic) 다른 응용 프로그램과 어셈블리 공유'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 520fe69d30ca55251ae7a19dcd7a1ea0c11e7bd5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59302221"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="e6eab-102">방법: (Visual Basic) 다른 응용 프로그램과 어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="e6eab-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="e6eab-103">어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 애플리케이션에서 사용되지 않으므로 전용 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="e6eab-104">다른 애플리케이션과 어셈블리를 공유하려면 GAC([전역 어셈블리 캐시](../../../../framework/app-domains/gac.md))에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="e6eab-105">어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="e6eab-105">Sharing an assembly</span></span>  
  
1. <span data-ttu-id="e6eab-106">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-106">Create your assembly.</span></span> <span data-ttu-id="e6eab-107">자세한 내용은 [어셈블리 만들기](../../../../framework/app-domains/create-assemblies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6eab-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2. <span data-ttu-id="e6eab-108">어셈블리에 강력한 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="e6eab-109">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6eab-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3. <span data-ttu-id="e6eab-110">어셈블리에 버전 정보를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-110">Assign version information to your assembly.</span></span> <span data-ttu-id="e6eab-111">자세한 내용은 [어셈블리 버전 관리](../../../../framework/app-domains/assembly-versioning.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6eab-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4. <span data-ttu-id="e6eab-112">전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="e6eab-113">자세한 내용은 [방법: 글로벌 어셈블리 캐시에 어셈블리 설치](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6eab-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5. <span data-ttu-id="e6eab-114">다른 애플리케이션에서 어셈블리에 포함된 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e6eab-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="e6eab-115">자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6eab-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6eab-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6eab-116">See also</span></span>

- [<span data-ttu-id="e6eab-117">프로그래밍 개념</span><span class="sxs-lookup"><span data-stu-id="e6eab-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="e6eab-118">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="e6eab-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="e6eab-119">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e6eab-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
