---
description: '자세히 알아보기: IMetaDataEmit2:: SaveDeltaToStream 메서드'
title: IMetaDataEmit2::SaveDeltaToStream 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: ce2e7822a5220a8ab1264a6e18337ba0f7828e3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771706"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="fa60e-103">IMetaDataEmit2::SaveDeltaToStream 메서드</span><span class="sxs-lookup"><span data-stu-id="fa60e-103">IMetaDataEmit2::SaveDeltaToStream Method</span></span>

<span data-ttu-id="fa60e-104">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 스트림에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa60e-104">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa60e-105">구문</span><span class="sxs-lookup"><span data-stu-id="fa60e-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa60e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fa60e-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="fa60e-107">진행 변경 내용을 저장할 쓰기 가능한 스트림에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fa60e-107">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="fa60e-108">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa60e-108">[in] Reserved.</span></span> <span data-ttu-id="fa60e-109">이 값은 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa60e-109">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa60e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fa60e-110">Requirements</span></span>  

 <span data-ttu-id="fa60e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa60e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa60e-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fa60e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa60e-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa60e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa60e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa60e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa60e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa60e-115">See also</span></span>

- [<span data-ttu-id="fa60e-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa60e-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="fa60e-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fa60e-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
