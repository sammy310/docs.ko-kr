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
ms.openlocfilehash: e8c145632911817e8e19d587bb8afead0a6c33af
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434339"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="b6361-102">IMetaDataEmit::DeleteToken 메서드</span><span class="sxs-lookup"><span data-stu-id="b6361-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="b6361-103">현재 메타 데이터 범위에서 지정 된 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6361-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6361-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6361-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6361-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6361-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="b6361-106">진행 삭제할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b6361-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6361-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6361-107">Requirements</span></span>  
 <span data-ttu-id="b6361-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6361-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6361-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b6361-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6361-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6361-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6361-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6361-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6361-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6361-112">See also</span></span>

- [<span data-ttu-id="b6361-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6361-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b6361-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6361-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
