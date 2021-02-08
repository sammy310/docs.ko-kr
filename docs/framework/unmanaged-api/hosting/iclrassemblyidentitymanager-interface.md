---
description: '자세히 알아보기: ICLRAssemblyIdentityManager 인터페이스'
title: ICLRAssemblyIdentityManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: d6238ec51a8cc1bb61eaa96e5297656c447df785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790058"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="1be80-103">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1be80-103">ICLRAssemblyIdentityManager Interface</span></span>

<span data-ttu-id="1be80-104">호스트와 어셈블리에 대 한 CLR (공용 언어 런타임) 간의 통신을 지 원하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-104">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1be80-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-105">Methods</span></span>  
  
|<span data-ttu-id="1be80-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-106">Method</span></span>|<span data-ttu-id="1be80-107">설명</span><span class="sxs-lookup"><span data-stu-id="1be80-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1be80-108">GetBindingIdentityFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-108">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="1be80-109">지정 된 파일 경로에서 어셈블리의 어셈블리 id 바인딩 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-109">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="1be80-110">GetBindingIdentityFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-110">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="1be80-111">지정 된 스트림의 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-111">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="1be80-112">GetCLRAssemblyReferenceList 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-112">GetCLRAssemblyReferenceList Method</span></span>](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="1be80-113">제공 된 부분 어셈블리 id 목록에서 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-113">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="1be80-114">GetProbingAssembliesFromReference 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-114">GetProbingAssembliesFromReference Method</span></span>](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="1be80-115">지정 된 id를 사용 하 여 어셈블리에서 참조 하는 어셈블리 id의 [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-115">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="1be80-116">GetReferencedAssembliesFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-116">GetReferencedAssembliesFromFile Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="1be80-117">지정 된 파일 경로에서 어셈블리가 참조 하는 어셈블리의 목록을 포함 하는 [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-117">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="1be80-118">GetReferencedAssembliesFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-118">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="1be80-119">지정 된 스트림의 어셈블리에서 참조 하는 어셈블리 `ICLRReferenceAssemblyEnum` 에 대 한 어셈블리 id 데이터를 포함 하는 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-119">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="1be80-120">IsStronglyNamed 메서드</span><span class="sxs-lookup"><span data-stu-id="1be80-120">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="1be80-121">지정 된 어셈블리에 강력한 이름이 지정 되었는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-121">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1be80-122">설명</span><span class="sxs-lookup"><span data-stu-id="1be80-122">Remarks</span></span>  

 <span data-ttu-id="1be80-123">를 사용 `ICLRAssemblyIdentityManager` 하 여 인스턴스를 가져오고 `ICLRAssemblyReferenceList` 어셈블리 id를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-123">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be80-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1be80-124">Requirements</span></span>  

 <span data-ttu-id="1be80-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1be80-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be80-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1be80-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1be80-127">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1be80-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1be80-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be80-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be80-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1be80-129">See also</span></span>

- [<span data-ttu-id="1be80-130">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1be80-130">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1be80-131">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1be80-131">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="1be80-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1be80-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
