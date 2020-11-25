---
title: IMetaDataEmit::DeleteClassLayout 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: d355e0e3b2461932384ca11d83d46fd1dc63b80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732686"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="4f0fb-102">IMetaDataEmit::DeleteClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="4f0fb-102">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="4f0fb-103">지정 된 토큰이 나타내는 형식에 대 한 클래스 레이아웃 메타 데이터 서명을 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4f0fb-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f0fb-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f0fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f0fb-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="4f0fb-106">진행 `mdTypeDef` 클래스 레이아웃을 삭제할 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0fb-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f0fb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f0fb-107">Requirements</span></span>  

 <span data-ttu-id="4f0fb-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f0fb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0fb-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4f0fb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f0fb-110">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0fb-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f0fb-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0fb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0fb-112">참조</span><span class="sxs-lookup"><span data-stu-id="4f0fb-112">See also</span></span>

- [<span data-ttu-id="4f0fb-113">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f0fb-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4f0fb-114">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f0fb-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
