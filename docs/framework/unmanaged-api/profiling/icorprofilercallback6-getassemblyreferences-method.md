---
title: ICorProfilerCallback6::GetAssemblyReferences 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerCallback6.GetAssemblyReferences
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: 8b391afb-d79f-41bd-94ce-43ce62c6b5fc
topic_type:
- apiref
ms.openlocfilehash: c9e973009f46ef7e554ee2df63493464f4956342
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725484"
---
# <a name="icorprofilercallback6getassemblyreferences-method"></a><span data-ttu-id="b3421-102">ICorProfilerCallback6::GetAssemblyReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="b3421-102">ICorProfilerCallback6::GetAssemblyReferences Method</span></span>

<span data-ttu-id="b3421-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="b3421-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b3421-104">공용 언어 런타임이 어셈블리 참조 closure 워커를 수행할 때 어셈블리가 초기 로드 상태임을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-104">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3421-105">구문</span><span class="sxs-lookup"><span data-stu-id="b3421-105">Syntax</span></span>  
  
```cpp
HRESULT GetAssemblyReferences(        [in, string] const WCHAR* wszAssemblyPath,  
        [in] ICorProfilerAssemblyReferenceProvider* pAsmRefProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3421-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3421-106">Parameters</span></span>  

 `wszAssemblyPath`  
 <span data-ttu-id="b3421-107">[in] 메타데이터를 수정할 어셈블리의 경로와 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-107">[in] The path and name of the assembly whose metadata will be modified.</span></span>  
  
 `pAsmRefProvider`  
 <span data-ttu-id="b3421-108">진행 추가할 어셈블리 참조를 지정 하는 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-108">[in] A pointer to the address of an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface that specifies the assembly references to add.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3421-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3421-109">Return Value</span></span>  

 <span data-ttu-id="b3421-110">이 콜백의 반환 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-110">Return values from this callback are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3421-111">설명</span><span class="sxs-lookup"><span data-stu-id="b3421-111">Remarks</span></span>  

 <span data-ttu-id="b3421-112">이 콜백은 [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출할 때 [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 설정 하 여 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-112">This callback is controlled by setting the [COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span> <span data-ttu-id="b3421-113">프로파일러가 [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) 콜백 메서드에 등록 하는 경우 런타임은 로드 될 어셈블리의 경로 및 이름과 해당 메서드에 대 한 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 인터페이스 개체에 대 한 포인터를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-113">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="b3421-114">그런 다음 프로파일러는 [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) `COR_PRF_ASSEMBLY_REFERENCE_INFO` 콜백에 지정 된 어셈블리에서 참조 하려는 각 대상 어셈블리에 대 한 개체를 사용 하 여 ICorProfilerAssemblyReferenceProvider:: addassemblyreference 메서드를 호출할 수 있습니다 `GetAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="b3421-114">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="b3421-115">프로파일러가 어셈블리 참조를 추가하기 위해 어셈블리 메타데이터를 수정해야 하는 경우에만 `GetAssemblyReferences` 콜백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-115">Use the `GetAssemblyReferences` callback only if the profiler has to modify an assembly's metadata to add assembly references.</span></span> <span data-ttu-id="b3421-116">그러나 어셈블리의 메타 데이터에 대 한 실제 수정은 [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)콜백 메서드에서 수행 됩니다. 프로파일러가 `GetAssemblyReferences` CLR (공용 언어 런타임)에 게 모듈 로드 시 어셈블리 참조가 추가 된다는 것을 알리기 위해 프로파일러는 콜백 메서드를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-116">(But note that the actual modification of an assembly's metadata is done in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)callback method.) The profiler should implement the `GetAssemblyReferences` callback method to inform the common language runtime (CLR) that assembly references will be added when the module has been loaded.</span></span>  <span data-ttu-id="b3421-117">그러면 프로파일러가 메타데이터 어셈블리 참조를 나중에 수정하더라도 이 초기 단계에서 CLR이 결정하는 어셈블리 공유 여부가 유효하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-117">This helps ensure that assembly sharing decisions made by the CLR during this early stage remain valid although the profiler plans to modify the metadata assembly references later.</span></span>  <span data-ttu-id="b3421-118">따라서 프로파일러 메타데이터 수정으로 인해 발생하는 `SECURITY_E_INCOMPATIBLE_SHARE` 오류 중 일부를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-118">This can avoid some instances in which profiler metadata modifications cause an `SECURITY_E_INCOMPATIBLE_SHARE` error.</span></span>  
  
 <span data-ttu-id="b3421-119">프로파일러에서는이 메서드에서 제공 하는 [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 개체를 사용 하 여 CLR 어셈블리 참조 클로저 walker에 어셈블리 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-119">The profiler uses the [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object provided by this method to add assembly references to the CLR assembly reference closure walker.</span></span>  <span data-ttu-id="b3421-120">[ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) 개체는이 콜백 내 에서만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-120">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) object should be used only from within this callback.</span></span> <span data-ttu-id="b3421-121">이 콜백에서 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 메서드를 호출 하면 수정 된 메타 데이터가 생성 되지 않지만 수정 된 어셈블리 참조 클로저 연습 에서만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-121">Calls to the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method from this callback don't result in modified metadata, but only in a modified assembly reference closure walk.</span></span> <span data-ttu-id="b3421-122">프로파일러는 콜백을 구현 하는 경우에도 [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) 개체를 사용 하 여 참조 하는 어셈블리에 대 한 [ICorProfilerCallback:: moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백 내에서 어셈블리 참조를 명시적으로 추가 해야 합니다 `GetAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="b3421-122">The profiler will still have to use an [IMetaDataAssemblyEmit](../metadata/imetadataassemblyemit-interface.md) object to explicitly add assembly references from within the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback for the referencing assembly, even if it implements the `GetAssemblyReferences` callback.</span></span>  
  
 <span data-ttu-id="b3421-123">프로파일러는 동일한 어셈블리에 대해이 콜백에 대 한 중복 호출을 받을 준비를 해야 하며, 동일한 [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) 호출 집합을 만들어 이러한 중복 호출에 대해 동일 하 게 응답 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3421-123">The profiler should be prepared to receive duplicate calls to this callback for the same assembly, and should respond identically for each such duplicate call (by making the same set of [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) calls).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3421-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3421-124">Requirements</span></span>  

 <span data-ttu-id="b3421-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3421-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3421-126">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3421-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3421-127">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3421-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3421-128">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3421-128">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3421-129">참조</span><span class="sxs-lookup"><span data-stu-id="b3421-129">See also</span></span>

- [<span data-ttu-id="b3421-130">ICorProfilerCallback6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3421-130">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)
- [<span data-ttu-id="b3421-131">ModuleLoadFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="b3421-131">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="b3421-132">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="b3421-132">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)
- [<span data-ttu-id="b3421-133">ICorProfilerAssemblyReferenceProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3421-133">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
