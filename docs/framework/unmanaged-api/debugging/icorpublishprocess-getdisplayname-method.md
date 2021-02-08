---
description: '자세히 알아보기: ICorPublishProcess:: GetDisplayName 메서드'
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
ms.openlocfilehash: 7aef55a40c24953766377f21e8291bceb1594480
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794587"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="7e71d-103">ICorPublishProcess::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="7e71d-103">ICorPublishProcess::GetDisplayName Method</span></span>

<span data-ttu-id="7e71d-104">이 [ICorPublishProcess](icorpublishprocess-interface.md)에서 참조 하는 프로세스에 대 한 실행 파일의 전체 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e71d-104">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e71d-105">구문</span><span class="sxs-lookup"><span data-stu-id="7e71d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e71d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e71d-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="7e71d-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7e71d-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7e71d-108">제한이 배열에 반환 된 와이드 문자의 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="7e71d-108">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e71d-109">제한이 실행 파일의 전체 경로를 포함 하 여 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e71d-109">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="7e71d-110">이름이 null로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e71d-110">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e71d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e71d-111">Requirements</span></span>  

 <span data-ttu-id="7e71d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e71d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e71d-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="7e71d-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7e71d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e71d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e71d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e71d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e71d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e71d-116">See also</span></span>

- [<span data-ttu-id="7e71d-117">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e71d-117">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
