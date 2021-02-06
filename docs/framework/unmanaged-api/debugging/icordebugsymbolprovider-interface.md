---
description: '자세히 알아보기: ICorDebugSymbolProvider 인터페이스'
title: ICorDebugSymbolProvider 인터페이스
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: bd47f294092ee87fc1f34bc68fe744b447e21f20
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659584"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="e902f-103">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e902f-103">ICorDebugSymbolProvider Interface</span></span>

<span data-ttu-id="e902f-104">디버그 기호 정보를 검색하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-104">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e902f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-105">Methods</span></span>  
  
|<span data-ttu-id="e902f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-106">Method</span></span>|<span data-ttu-id="e902f-107">설명</span><span class="sxs-lookup"><span data-stu-id="e902f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e902f-108">GetAssemblyImageBytes 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-108">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="e902f-109">병합된 어셈블리의 RVA(상대 가상 주소)가 지정된 경우 병합된 어셈블리에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-109">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="e902f-110">GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-110">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="e902f-111">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-111">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="e902f-112">GetCodeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-112">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="e902f-113">메서드의 RVA(상대 가상 주소)가 지정된 경우 메서드 시작 주소와 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-113">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="e902f-114">GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-114">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="e902f-115">typespec 서명에 해당하는 인스턴스 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-115">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e902f-116">GetMergedAssemblyRecords 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-116">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="e902f-117">모든 병합된 어셈블리에 대한 기호 레코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-117">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="e902f-118">GetMethodLocalSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-118">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="e902f-119">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 로컬 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-119">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e902f-120">GetMethodParameterSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-120">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="e902f-121">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 매개 변수 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-121">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="e902f-122">GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-122">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="e902f-123">해당 메서드에 RVA(상대 가상 주소)가 제공된 경우 메서드의 메타데이터 토큰 및 제네릭 매개 변수 정보와 같은 메서드 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-123">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="e902f-124">GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-124">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="e902f-125">typespec 서명을 기준으로 개체의 개체 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-125">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="e902f-126">GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-126">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="e902f-127">typespec 서명에 해당하는 정적 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-127">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="e902f-128">GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e902f-128">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="e902f-129">vtable에 RVA(상대 가상 주소)가 제공된 경우 해당 제네릭 매개 변수의 서명 수와 같은 형식의 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-129">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e902f-130">설명</span><span class="sxs-lookup"><span data-stu-id="e902f-130">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e902f-131">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-131">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e902f-132">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="e902f-132">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e902f-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e902f-133">Requirements</span></span>  

 <span data-ttu-id="e902f-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e902f-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e902f-135">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e902f-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e902f-136">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e902f-136">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e902f-137">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e902f-137">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e902f-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e902f-138">See also</span></span>

- [<span data-ttu-id="e902f-139">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e902f-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e902f-140">디버깅</span><span class="sxs-lookup"><span data-stu-id="e902f-140">Debugging</span></span>](index.md)
