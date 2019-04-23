---
title: IMetaDataEmit::DeleteToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d85fb62936678f830ca7eaf26a97c36be5f23ac8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138244"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="bd77e-102">IMetaDataEmit::DeleteToken 메서드</span><span class="sxs-lookup"><span data-stu-id="bd77e-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="bd77e-103">현재 메타 데이터 범위에서 지정된 된 토큰을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bd77e-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd77e-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd77e-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd77e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd77e-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="bd77e-106">[in] 삭제할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bd77e-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd77e-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd77e-107">Requirements</span></span>  
 <span data-ttu-id="bd77e-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd77e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd77e-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd77e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd77e-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bd77e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd77e-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd77e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd77e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="bd77e-112">See also</span></span>

- [<span data-ttu-id="bd77e-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd77e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bd77e-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd77e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
