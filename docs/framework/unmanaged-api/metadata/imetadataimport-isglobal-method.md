---
title: IMetaDataImport::IsGlobal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
ms.openlocfilehash: d477976952d2c1875a620d1397fd43e5c5e2836f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503473"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="31fe0-102">IMetaDataImport::IsGlobal 메서드</span><span class="sxs-lookup"><span data-stu-id="31fe0-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="31fe0-103">지정한 메타데이터 토큰이 나타내는 필드, 메서드 또는 형식에 전역 범위가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31fe0-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31fe0-104">구문</span><span class="sxs-lookup"><span data-stu-id="31fe0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31fe0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31fe0-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="31fe0-106">진행 형식, 필드 또는 메서드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="31fe0-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="31fe0-107">[out] 1 (개체가 전역 범위를 포함 하는 경우) 그렇지 않으면 0이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fe0-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31fe0-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31fe0-108">Requirements</span></span>  
 <span data-ttu-id="31fe0-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31fe0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31fe0-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="31fe0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31fe0-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31fe0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31fe0-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31fe0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fe0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31fe0-113">See also</span></span>

- [<span data-ttu-id="31fe0-114">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31fe0-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="31fe0-115">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31fe0-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
