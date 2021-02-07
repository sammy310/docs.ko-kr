---
description: '자세히 알아보기: ICorProfilerInfo2:: GetStaticFieldInfo 메서드'
title: ICorProfilerInfo2::GetStaticFieldInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: 1acde9d5ad1a35b11cb036bced99c1909f0b6b04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716359"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="023d1-103">ICorProfilerInfo2::GetStaticFieldInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="023d1-103">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>

<span data-ttu-id="023d1-104">지정 된 필드에 적용 되는 정적의 종류를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-104">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="023d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="023d1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="023d1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="023d1-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="023d1-107">진행 정적 필드가 정의 된 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-107">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="023d1-108">진행 정적 필드에 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-108">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="023d1-109">제한이 지정 된 필드가 정적 인지 여부를 나타내는 [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) 열거형 값에 대 한 포인터이 고, 그렇지 않으면 필드에 적용 되는 정적의 종류입니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-109">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="023d1-110">설명</span><span class="sxs-lookup"><span data-stu-id="023d1-110">Remarks</span></span>  

 <span data-ttu-id="023d1-111">이 정보는 정적 필드의 주소를 가져오기 위해 호출할 함수를 결정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-111">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="023d1-112">프로파일러 코드는 여전히 정적 필드에 대 한 메타 데이터를 확인 하 여 실제로 주소가 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-112">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="023d1-113">정적 리터럴 (즉, 상수)은 메타 데이터에만 존재 하 고 주소는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="023d1-113">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="023d1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="023d1-114">Requirements</span></span>  

 <span data-ttu-id="023d1-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="023d1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="023d1-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="023d1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="023d1-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="023d1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="023d1-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="023d1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023d1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="023d1-119">See also</span></span>

- [<span data-ttu-id="023d1-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="023d1-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="023d1-121">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="023d1-121">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
