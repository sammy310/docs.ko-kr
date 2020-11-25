---
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
ms.openlocfilehash: cef238239417a0a30cd94eaa8bd60968cfa78859
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722000"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="8d72b-102">IMetaDataEmit::Save 메서드</span><span class="sxs-lookup"><span data-stu-id="8d72b-102">IMetaDataEmit::Save Method</span></span>

<span data-ttu-id="8d72b-103">현재 범위에 있는 모든 메타 데이터를 지정 된 주소에 있는 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d72b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d72b-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d72b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d72b-105">Parameters</span></span>  

 `wzFile`  
 <span data-ttu-id="8d72b-106">진행 저장할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="8d72b-107">이 값이 null 이면 메모리 내 복사본이 사용 된 마지막 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="8d72b-108">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-108">[in] Reserved.</span></span> <span data-ttu-id="8d72b-109">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d72b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d72b-110">Requirements</span></span>  

 <span data-ttu-id="8d72b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d72b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d72b-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8d72b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d72b-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d72b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d72b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d72b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d72b-115">참조</span><span class="sxs-lookup"><span data-stu-id="8d72b-115">See also</span></span>

- [<span data-ttu-id="8d72b-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d72b-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8d72b-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d72b-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
