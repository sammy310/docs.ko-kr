---
title: 어셈블리 및 DLL의 이름
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744164"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="e8003-102">어셈블리 및 DLL의 이름</span><span class="sxs-lookup"><span data-stu-id="e8003-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="e8003-103">어셈블리는 관리 코드 프로그램에 대 한 배포 및 id의 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="e8003-104">어셈블리는 하나 이상의 파일에 걸쳐 있을 수 있지만 일반적으로 어셈블리는 어셈블리를 사용 하 여 일대일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="e8003-105">따라서이 섹션에서는 DLL 명명 규칙에 대해서만 설명 하며,이 규칙을 어셈블리 명명 규칙에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="e8003-106">✔️는 System.object와 같이 많은 양의 기능을 제안 하는 어셈블리 Dll의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-106">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="e8003-107">어셈블리 및 DLL 이름은 네임 스페이스 이름과 일치 하지 않아도 되지만 어셈블리 이름을 지정할 때 네임 스페이스 이름을 따르는 것이 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="e8003-108">좋은 방법은 어셈블리에 포함 된 네임 스페이스의 공통 접두사를 기반으로 DLL의 이름을 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="e8003-109">예를 들어, `MyCompany.MyTechnology.FirstFeature` 및 `MyCompany.MyTechnology.SecondFeature`라는 두 개의 네임 스페이스를 포함 하는 어셈블리를 `MyCompany.MyTechnology.dll`호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="e8003-110">다음 패턴에 따라 Dll의 이름을 지정 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="e8003-110">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="e8003-111">여기서 `<Component>`에는 점으로 구분 된 절이 하나 이상 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8003-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="e8003-112">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="e8003-112">For example:</span></span>

 <span data-ttu-id="e8003-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="e8003-113">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="e8003-114">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="e8003-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="e8003-115">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="e8003-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="e8003-116">참조</span><span class="sxs-lookup"><span data-stu-id="e8003-116">See also</span></span>

- [<span data-ttu-id="e8003-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="e8003-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e8003-118">명명 지침</span><span class="sxs-lookup"><span data-stu-id="e8003-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
