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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e45085b0fbca10e490f11ce588f68aa8237b46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043058"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="dc268-102">IMetaDataEmit::Save 메서드</span><span class="sxs-lookup"><span data-stu-id="dc268-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="dc268-103">지정된 된 주소에서 파일을 현재 범위에서 모든 메타 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dc268-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc268-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc268-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc268-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc268-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="dc268-106">[in] 저장할 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dc268-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="dc268-107">이 값이 null 이면 위치는 데 사용 된 메모리 내 복사본 마지막 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc268-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="dc268-108">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc268-108">[in] Reserved.</span></span> <span data-ttu-id="dc268-109">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc268-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc268-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc268-110">Requirements</span></span>  
 <span data-ttu-id="dc268-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc268-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc268-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc268-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc268-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="dc268-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc268-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc268-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc268-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc268-115">See also</span></span>

- [<span data-ttu-id="dc268-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc268-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dc268-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc268-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
