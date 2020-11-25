---
title: 어셈블리 및 DLL의 이름
description: 어셈블리 및 Dll (동적 연결 라이브러리)의 이름을 지정 하는 방법에 대 한 지침을 알아봅니다. 어셈블리는 하나 이상의 파일에 걸쳐 있을 수 있지만 일반적으로 하나 이상의 파일에 매핑할 수 있습니다.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: 95a90ff66ffc9f2a5a3202d6877b1cc19149ff35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706530"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="89a1e-104">어셈블리 및 DLL의 이름</span><span class="sxs-lookup"><span data-stu-id="89a1e-104">Names of Assemblies and DLLs</span></span>

<span data-ttu-id="89a1e-105">어셈블리는 관리 코드 프로그램에 대 한 배포 및 id의 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-105">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="89a1e-106">어셈블리는 하나 이상의 파일에 걸쳐 있을 수 있지만 일반적으로 어셈블리는 어셈블리를 사용 하 여 일대일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-106">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="89a1e-107">따라서이 섹션에서는 DLL 명명 규칙에 대해서만 설명 하며,이 규칙을 어셈블리 명명 규칙에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-107">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="89a1e-108">✔️는 System.object와 같이 많은 양의 기능을 제안 하는 어셈블리 Dll의 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-108">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="89a1e-109">어셈블리 및 DLL 이름은 네임 스페이스 이름과 일치 하지 않아도 되지만 어셈블리 이름을 지정할 때 네임 스페이스 이름을 따르는 것이 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-109">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="89a1e-110">좋은 방법은 어셈블리에 포함 된 네임 스페이스의 공통 접두사를 기반으로 DLL의 이름을 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-110">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="89a1e-111">예를 들어, 및 라는 두 네임 스페이스를 포함 하는 어셈블리를 `MyCompany.MyTechnology.FirstFeature` `MyCompany.MyTechnology.SecondFeature` 호출할 수 있습니다 `MyCompany.MyTechnology.dll` .</span><span class="sxs-lookup"><span data-stu-id="89a1e-111">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="89a1e-112">다음 패턴에 따라 Dll의 이름을 지정 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="89a1e-112">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="89a1e-113">여기 `<Component>` 에는 점으로 구분 된 절이 하나 이상 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-113">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="89a1e-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89a1e-114">For example:</span></span>

 <span data-ttu-id="89a1e-115">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="89a1e-115">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="89a1e-116">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="89a1e-116">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="89a1e-117">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="89a1e-117">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="89a1e-118">참조</span><span class="sxs-lookup"><span data-stu-id="89a1e-118">See also</span></span>

- [<span data-ttu-id="89a1e-119">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="89a1e-119">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="89a1e-120">명명 지침</span><span class="sxs-lookup"><span data-stu-id="89a1e-120">Naming Guidelines</span></span>](naming-guidelines.md)
