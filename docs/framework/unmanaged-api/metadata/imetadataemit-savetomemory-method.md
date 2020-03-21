---
title: IMetaDataEmit::SaveToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: d8843b2b5f69696dc206e9b530e3062ff225e89e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177576"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="b6e40-102">IMetaDataEmit::SaveToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="b6e40-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="b6e40-103">현재 범위의 모든 메타데이터를 지정된 메모리 영역에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e40-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6e40-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6e40-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6e40-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6e40-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="b6e40-106">【아웃】 메타데이터 작성을 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e40-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="b6e40-107">【인】 할당된 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e40-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6e40-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6e40-108">Requirements</span></span>  
 <span data-ttu-id="b6e40-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6e40-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6e40-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b6e40-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6e40-111">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b6e40-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6e40-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6e40-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e40-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6e40-113">See also</span></span>

- [<span data-ttu-id="b6e40-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6e40-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b6e40-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6e40-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
