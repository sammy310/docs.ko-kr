---
description: '자세히 알아보기: IMetaDataImport:: GetModuleFromScope 메서드'
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
ms.openlocfilehash: 8c1e952a45b3827717102428fbd18ceac3951baf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753369"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="ba76c-103">IMetaDataImport::GetModuleFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="ba76c-103">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="ba76c-104">현재 메타 데이터 범위에서 참조 되는 모듈에 대 한 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba76c-104">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba76c-105">구문</span><span class="sxs-lookup"><span data-stu-id="ba76c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba76c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba76c-106">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="ba76c-107">제한이 현재 메타 데이터 범위에서 참조 되는 모듈을 나타내는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba76c-107">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba76c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba76c-108">Requirements</span></span>  

 <span data-ttu-id="ba76c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba76c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba76c-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ba76c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba76c-111">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba76c-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba76c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba76c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba76c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba76c-113">See also</span></span>

- [<span data-ttu-id="ba76c-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba76c-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ba76c-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba76c-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
