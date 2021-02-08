---
description: IMetaDataEmit::D eleteClassLayout 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 44be89f415087a1457a83bb1167e1017d26ed5ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783991"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="1090f-103">IMetaDataEmit::DeleteClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="1090f-103">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="1090f-104">지정 된 토큰이 나타내는 형식에 대 한 클래스 레이아웃 메타 데이터 서명을 소멸 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1090f-104">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1090f-105">구문</span><span class="sxs-lookup"><span data-stu-id="1090f-105">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1090f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1090f-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="1090f-107">진행 `mdTypeDef` 클래스 레이아웃을 삭제할 형식을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1090f-107">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1090f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1090f-108">Requirements</span></span>  

 <span data-ttu-id="1090f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1090f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1090f-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1090f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1090f-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1090f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1090f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1090f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1090f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1090f-113">See also</span></span>

- [<span data-ttu-id="1090f-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1090f-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1090f-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1090f-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
