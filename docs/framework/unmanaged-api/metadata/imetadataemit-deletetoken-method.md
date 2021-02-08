---
description: IMetaDataEmit::D eleteToken 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 5c28b56b06f994057409ef8fa17179cb0b0e205b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783952"
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="124cb-103">IMetaDataEmit::DeleteToken 메서드</span><span class="sxs-lookup"><span data-stu-id="124cb-103">IMetaDataEmit::DeleteToken Method</span></span>

<span data-ttu-id="124cb-104">현재 메타 데이터 범위에서 지정 된 토큰을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="124cb-104">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="124cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="124cb-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteToken (
    [in]  mdToken     tkObj
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="124cb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="124cb-106">Parameters</span></span>  

 `tkObj`  
 <span data-ttu-id="124cb-107">진행 삭제할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="124cb-107">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="124cb-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="124cb-108">Requirements</span></span>  

 <span data-ttu-id="124cb-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="124cb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="124cb-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="124cb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="124cb-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="124cb-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="124cb-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="124cb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="124cb-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="124cb-113">See also</span></span>

- [<span data-ttu-id="124cb-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="124cb-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="124cb-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="124cb-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
