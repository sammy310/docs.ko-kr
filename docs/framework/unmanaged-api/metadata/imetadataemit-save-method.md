---
description: '자세히 알아보기: IMetaDataEmit:: Save 메서드'
title: IMetaDataEmit::Save 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: bf8675540ae2c851d2b6ed14883c9b75e9631903
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745868"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="af482-103">IMetaDataEmit::Save 메서드</span><span class="sxs-lookup"><span data-stu-id="af482-103">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="af482-104">현재 범위에 있는 모든 메타 데이터를 지정 된 주소에 있는 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="af482-104">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af482-105">구문</span><span class="sxs-lookup"><span data-stu-id="af482-105">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af482-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af482-106">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="af482-107">진행 저장할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="af482-107">[in] The name of the file to save to.</span></span> <span data-ttu-id="af482-108">이 값이 null 이면 메모리 내 복사본이 사용 된 마지막 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af482-108">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="af482-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af482-109">[in] Reserved.</span></span> <span data-ttu-id="af482-110">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af482-110">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af482-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af482-111">Requirements</span></span>  

 <span data-ttu-id="af482-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af482-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af482-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="af482-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af482-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af482-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af482-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af482-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af482-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af482-116">See also</span></span>

- [<span data-ttu-id="af482-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af482-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="af482-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af482-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
