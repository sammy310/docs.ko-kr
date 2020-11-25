---
title: IMetaDataImport::GetModuleFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 2eddd7a80c2b9c1b71f3e7fc5b1e4686ba11bccd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733167"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="317da-102">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="317da-102">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="317da-103">현재 메타 데이터 범위에서 참조 되는 모듈에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="317da-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317da-104">구문</span><span class="sxs-lookup"><span data-stu-id="317da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="317da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="317da-105">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="317da-106">제한이 현재 메타 데이터 범위에서 참조 되는 모듈을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="317da-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317da-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="317da-107">Requirements</span></span>  

 <span data-ttu-id="317da-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="317da-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317da-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="317da-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="317da-110">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="317da-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="317da-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317da-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317da-112">참조</span><span class="sxs-lookup"><span data-stu-id="317da-112">See also</span></span>

- [<span data-ttu-id="317da-113">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="317da-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="317da-114">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="317da-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
