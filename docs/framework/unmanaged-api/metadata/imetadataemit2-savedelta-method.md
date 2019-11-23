---
title: IMetaDataEmit2::SaveDelta 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: afb0c09c09236267be2a999ce5c130feebb52b6f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447900"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="1d648-102">IMetaDataEmit2::SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="1d648-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="1d648-103">Saves changes from the current edit-and-continue session to the specified file.</span><span class="sxs-lookup"><span data-stu-id="1d648-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d648-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d648-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d648-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d648-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="1d648-106">[in] The file name under which to save changes.</span><span class="sxs-lookup"><span data-stu-id="1d648-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="1d648-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d648-107">[in] Reserved.</span></span> <span data-ttu-id="1d648-108">Must be zero.</span><span class="sxs-lookup"><span data-stu-id="1d648-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d648-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d648-109">Requirements</span></span>  
 <span data-ttu-id="1d648-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d648-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d648-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d648-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d648-112">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d648-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d648-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d648-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d648-114">참조</span><span class="sxs-lookup"><span data-stu-id="1d648-114">See also</span></span>

- [<span data-ttu-id="1d648-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d648-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="1d648-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d648-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
