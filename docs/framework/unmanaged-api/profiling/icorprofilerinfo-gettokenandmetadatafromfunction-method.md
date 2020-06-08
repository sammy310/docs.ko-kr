---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
ms.openlocfilehash: 1cc05f4c10f4a5b042ff14c05f3c85a7b5935184
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497896"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="430d6-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="430d6-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="430d6-103">지정 된 함수에 대 한 토큰에 대해 사용할 수 있는 메타 데이터 토큰 및 메타 데이터 인터페이스 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="430d6-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="430d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="430d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="430d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="430d6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="430d6-106">진행 메타 데이터 토큰 및 메타 데이터 인터페이스를 가져올 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="430d6-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="430d6-107">진행 인스턴스를 가져올 메타 데이터 인터페이스의 참조 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="430d6-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="430d6-108">제한이 지정 된 함수에 대 한 토큰에 대해 사용할 수 있는 메타 데이터 인터페이스 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="430d6-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="430d6-109">제한이 지정 된 함수에 대 한 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="430d6-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="430d6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="430d6-110">Requirements</span></span>  
 <span data-ttu-id="430d6-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430d6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="430d6-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="430d6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="430d6-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="430d6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="430d6-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="430d6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430d6-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="430d6-115">See also</span></span>

- [<span data-ttu-id="430d6-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="430d6-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
