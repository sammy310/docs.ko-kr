---
title: IMetaDataEmit::SaveToStream 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175683"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="daab9-102">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="daab9-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="daab9-103">현재 범위의 모든 메타데이터를 지정된 `IStream`에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="daab9-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daab9-104">구문</span><span class="sxs-lookup"><span data-stu-id="daab9-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daab9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daab9-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="daab9-106">【인】 저장할 쓰기 가능한 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="daab9-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="daab9-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daab9-107">[in] Reserved.</span></span> <span data-ttu-id="daab9-108">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daab9-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daab9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daab9-109">Requirements</span></span>  
 <span data-ttu-id="daab9-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daab9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daab9-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="daab9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="daab9-112">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="daab9-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daab9-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daab9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daab9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daab9-114">See also</span></span>

- [<span data-ttu-id="daab9-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daab9-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="daab9-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daab9-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
