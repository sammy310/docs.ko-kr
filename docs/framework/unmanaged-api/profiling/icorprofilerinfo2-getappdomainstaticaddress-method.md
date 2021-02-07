---
description: '자세히 알아보기: ICorProfilerInfo2:: GetAppDomainStaticAddress 메서드'
title: ICorProfilerInfo2::GetAppDomainStaticAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 4ef8511e75a18f7626fa7a30ea194140de051bb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753239"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="ef93a-103">ICorProfilerInfo2::GetAppDomainStaticAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ef93a-103">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>

<span data-ttu-id="ef93a-104">지정 된 응용 프로그램 도메인의 범위에 있는 지정 된 응용 프로그램 도메인 정적 필드의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-104">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef93a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ef93a-105">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef93a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef93a-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="ef93a-107">진행 요청 된 응용 프로그램 도메인 정적 필드를 포함 하는 클래스의 클래스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-107">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="ef93a-108">진행 요청 된 응용 프로그램 도메인 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-108">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="ef93a-109">진행 요청 된 정적 필드의 범위에 해당 하는 응용 프로그램 도메인의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-109">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="ef93a-110">제한이 지정 된 응용 프로그램 도메인 내에 있는 정적 필드의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-110">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef93a-111">설명</span><span class="sxs-lookup"><span data-stu-id="ef93a-111">Remarks</span></span>  

 <span data-ttu-id="ef93a-112">`GetAppDomainStaticAddress`메서드는 다음 중 하나를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-112">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="ef93a-113">지정 된 컨텍스트에서 지정 된 정적 필드에 주소가 할당 되지 않은 경우 HRESULT CORPROF_E_DATAINCOMPLETE입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="ef93a-114">가비지 컬렉션 힙에 있을 수 있는 개체의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="ef93a-115">이러한 주소는 가비지 수집 후에 무효화 될 수 있으므로 가비지 수집 후 프로파일러는 이러한 주소를 유효한 것으로 가정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="ef93a-116">클래스의 클래스 생성자가 완료 되기 전에는 `GetAppDomainStaticAddress` 모든 정적 필드에 대 한 CORPROF_E_DATAINCOMPLETE를 반환 하지만, 일부 정적 필드는 이미 초기화 되 고 가비지 수집 개체를 루 팅 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef93a-116">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef93a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef93a-117">Requirements</span></span>  

 <span data-ttu-id="ef93a-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef93a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef93a-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef93a-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef93a-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef93a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef93a-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef93a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef93a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef93a-122">See also</span></span>

- [<span data-ttu-id="ef93a-123">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef93a-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ef93a-124">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef93a-124">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
