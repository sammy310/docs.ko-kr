---
title: ICorDebugSymbolProvider 인터페이스
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 25faad4f4bc67b57c339bc63d1a18ab4d275cd71
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379347"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="23f38-102">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23f38-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="23f38-103">디버그 기호 정보를 검색하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23f38-104">메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-104">Methods</span></span>  
  
|<span data-ttu-id="23f38-105">메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-105">Method</span></span>|<span data-ttu-id="23f38-106">설명</span><span class="sxs-lookup"><span data-stu-id="23f38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23f38-107">GetAssemblyImageBytes 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="23f38-108">병합된 어셈블리의 RVA(상대 가상 주소)가 지정된 경우 병합된 어셈블리에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="23f38-109">GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="23f38-110">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="23f38-111">GetCodeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="23f38-112">메서드의 RVA(상대 가상 주소)가 지정된 경우 메서드 시작 주소와 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="23f38-113">GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="23f38-114">typespec 서명에 해당하는 인스턴스 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="23f38-115">GetMergedAssemblyRecords 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="23f38-116">모든 병합된 어셈블리에 대한 기호 레코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="23f38-117">GetMethodLocalSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="23f38-118">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 로컬 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="23f38-119">GetMethodParameterSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="23f38-120">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 매개 변수 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="23f38-121">GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="23f38-122">해당 메서드에 RVA(상대 가상 주소)가 제공된 경우 메서드의 메타데이터 토큰 및 제네릭 매개 변수 정보와 같은 메서드 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="23f38-123">GetObjectSize 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="23f38-124">typespec 서명을 기준으로 개체의 개체 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="23f38-125">GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="23f38-126">typespec 서명에 해당하는 정적 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="23f38-127">GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="23f38-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="23f38-128">vtable에 RVA(상대 가상 주소)가 제공된 경우 해당 제네릭 매개 변수의 서명 수와 같은 형식의 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23f38-129">설명</span><span class="sxs-lookup"><span data-stu-id="23f38-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23f38-130">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="23f38-131">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="23f38-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f38-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23f38-132">Requirements</span></span>  
 <span data-ttu-id="23f38-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23f38-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f38-134">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23f38-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23f38-135">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23f38-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23f38-136">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f38-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f38-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23f38-137">See also</span></span>

- [<span data-ttu-id="23f38-138">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23f38-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="23f38-139">디버깅</span><span class="sxs-lookup"><span data-stu-id="23f38-139">Debugging</span></span>](index.md)
