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
ms.openlocfilehash: 77e801b048709949c384f642fc0d0ecb5d7eb512
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178389"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="de141-102">ICorPublishProcess::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="de141-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="de141-103">이 [ICorPublishProcess](icorpublishprocess-interface.md)에서 참조하는 프로세스에 대한 실행 의 전체 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="de141-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de141-104">구문</span><span class="sxs-lookup"><span data-stu-id="de141-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de141-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de141-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="de141-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="de141-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="de141-107">【아웃】 배열에서 반환되는 와이드 `szName` 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="de141-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="de141-108">【아웃】 실행 의 전체 경로를 포함하여 이름을 저장하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="de141-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="de141-109">이름은 null-종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="de141-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de141-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de141-110">Requirements</span></span>  
 <span data-ttu-id="de141-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de141-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de141-112">**헤더:** 코르펍.idl, 코르펍.h</span><span class="sxs-lookup"><span data-stu-id="de141-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="de141-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de141-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de141-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de141-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de141-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de141-115">See also</span></span>

- [<span data-ttu-id="de141-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de141-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
