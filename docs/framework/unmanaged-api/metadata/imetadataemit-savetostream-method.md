---
description: '자세히 알아보기: IMetaDataEmit:: SaveToStream 메서드'
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
ms.openlocfilehash: 104aa0b0dfcd0f4f9e8b87b4633880f6423f92d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706658"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="d77e5-103">IMetaDataEmit::SaveToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="d77e5-103">IMetaDataEmit::SaveToStream Method</span></span>

<span data-ttu-id="d77e5-104">현재 범위에 있는 모든 메타 데이터를 지정 된에 저장 `IStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77e5-104">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77e5-105">구문</span><span class="sxs-lookup"><span data-stu-id="d77e5-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d77e5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d77e5-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="d77e5-107">진행 저장할 쓰기 가능한 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="d77e5-107">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d77e5-108">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d77e5-108">[in] Reserved.</span></span> <span data-ttu-id="d77e5-109">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77e5-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d77e5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d77e5-110">Requirements</span></span>  

 <span data-ttu-id="d77e5-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d77e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d77e5-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d77e5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d77e5-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d77e5-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d77e5-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d77e5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77e5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d77e5-115">See also</span></span>

- [<span data-ttu-id="d77e5-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d77e5-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d77e5-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d77e5-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
