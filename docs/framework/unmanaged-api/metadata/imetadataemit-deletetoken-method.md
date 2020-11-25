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
ms.openlocfilehash: eaa465855c9e933286bcdd189e62048510088ec7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722078"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="21216-102">IMetaDataEmit::DeleteToken 메서드</span><span class="sxs-lookup"><span data-stu-id="21216-102">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="21216-103">현재 메타 데이터 범위에서 지정 된 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="21216-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21216-104">구문</span><span class="sxs-lookup"><span data-stu-id="21216-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21216-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21216-105">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="21216-106">진행 삭제할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="21216-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21216-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21216-107">Requirements</span></span>  

 <span data-ttu-id="21216-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21216-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21216-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="21216-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21216-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21216-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21216-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21216-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21216-112">참조</span><span class="sxs-lookup"><span data-stu-id="21216-112">See also</span></span>

- [<span data-ttu-id="21216-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21216-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="21216-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21216-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
