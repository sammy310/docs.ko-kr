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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d97f536d54ac1cb77c5d0413d2437508374ac7f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169002"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="6a174-102">IMetaDataEmit2::SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="6a174-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="6a174-103">편집 하며 계속 하기는 현재 세션에서 지정된 된 파일 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a174-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a174-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a174-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a174-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a174-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="6a174-106">[in] 변경 내용을 저장 하는 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a174-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="6a174-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a174-107">[in] Reserved.</span></span> <span data-ttu-id="6a174-108">0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a174-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a174-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a174-109">Requirements</span></span>  
 <span data-ttu-id="6a174-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a174-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a174-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a174-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a174-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="6a174-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6a174-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="6a174-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a174-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a174-114">See also</span></span>

- [<span data-ttu-id="6a174-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a174-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="6a174-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a174-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
