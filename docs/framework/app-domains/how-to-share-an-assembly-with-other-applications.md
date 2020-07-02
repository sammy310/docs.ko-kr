---
title: '방법: 다른 애플리케이션과 어셈블리 공유'
description: .NET에서 다른 애플리케이션과 어셈블리를 공유하는 방법을 참조하세요. 어셈블리는 프라이빗(기본값) 또는 공유일 수 있습니다. 어셈블리를 공유하려면 GAC에 어셈블리를 배치합니다.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 9cef25059968875f17ce5dc77b04c44a2f3945f6
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104654"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="8e536-105">방법: 다른 애플리케이션과 어셈블리 공유</span><span class="sxs-lookup"><span data-stu-id="8e536-105">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="8e536-106">어셈블리는 전용이거나 공유될 수 있습니다. 기본적으로 대부분의 간단한 프로그램은 다른 애플리케이션에서 사용되지 않으므로 프라이빗 어셈블리로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="8e536-107">다른 애플리케이션과 어셈블리를 공유하려면 [전역 어셈블리 캐시(GAC)](gac.md)에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="8e536-108">어셈블리를 공유하려면:</span><span class="sxs-lookup"><span data-stu-id="8e536-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="8e536-109">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-109">Create your assembly.</span></span> <span data-ttu-id="8e536-110">자세한 내용은 [어셈블리 만들기](../../standard/assembly/create.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e536-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="8e536-111">어셈블리에 강력한 이름을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="8e536-112">자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../standard/assembly/sign-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e536-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="8e536-113">어셈블리에 버전 정보를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-113">Assign version information to your assembly.</span></span> <span data-ttu-id="8e536-114">자세한 내용은 [어셈블리 버전 관리](../../standard/assembly/versioning.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e536-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="8e536-115">전역 어셈블리 캐시에 어셈블리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="8e536-116">자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](install-assembly-into-gac.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e536-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="8e536-117">다른 애플리케이션에서 어셈블리에 포함된 형식에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="8e536-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="8e536-118">자세한 내용은 [방법: 강력한 이름의 어셈블리 참조](../../standard/assembly/reference-strong-named.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e536-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e536-119">참조</span><span class="sxs-lookup"><span data-stu-id="8e536-119">See also</span></span>

- [<span data-ttu-id="8e536-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8e536-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="8e536-121">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e536-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="8e536-122">어셈블리를 사용한 프로그램</span><span class="sxs-lookup"><span data-stu-id="8e536-122">Program with assemblies</span></span>](../../standard/assembly/index.md)
