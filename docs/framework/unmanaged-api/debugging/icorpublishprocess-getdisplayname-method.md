---
title: ICorPublishProcess::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 354e1b0dad942534068d5fb07071ed4ac695fb49
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764891"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="bd89b-102">ICorPublishProcess::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="bd89b-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="bd89b-103">이 참조 하는 프로세스에 대 한 실행 파일의 전체 경로 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd89b-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd89b-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd89b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd89b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd89b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="bd89b-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89b-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="bd89b-107">[out] 반환 하는 와이드 문자 수는 `szName` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89b-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="bd89b-108">[out] 실행 파일의 전체 경로 포함 하는 이름을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89b-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="bd89b-109">이름은은 null로 끝나는입니다.</span><span class="sxs-lookup"><span data-stu-id="bd89b-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd89b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd89b-110">Requirements</span></span>  
 <span data-ttu-id="bd89b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd89b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd89b-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="bd89b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bd89b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd89b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd89b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd89b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd89b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bd89b-115">See also</span></span>

- [<span data-ttu-id="bd89b-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd89b-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
