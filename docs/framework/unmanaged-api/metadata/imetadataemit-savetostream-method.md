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
ms.openlocfilehash: 3f8da08b96c47c90ecccae28dd1662a7abffaf1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688564"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="6c07a-102">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="6c07a-102">IMetaDataEmit::SaveToStream Method</span></span>

<span data-ttu-id="6c07a-103">현재 범위에 있는 모든 메타 데이터를 지정 된에 저장 `IStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c07a-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c07a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c07a-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c07a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c07a-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="6c07a-106">진행 저장할 쓰기 가능한 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="6c07a-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="6c07a-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c07a-107">[in] Reserved.</span></span> <span data-ttu-id="6c07a-108">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c07a-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c07a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c07a-109">Requirements</span></span>  

 <span data-ttu-id="6c07a-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c07a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c07a-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6c07a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c07a-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c07a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c07a-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c07a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c07a-114">참조</span><span class="sxs-lookup"><span data-stu-id="6c07a-114">See also</span></span>

- [<span data-ttu-id="6c07a-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c07a-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6c07a-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c07a-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
