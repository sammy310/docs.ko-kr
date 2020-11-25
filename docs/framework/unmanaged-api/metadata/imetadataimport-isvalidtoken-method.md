---
title: IMetaDataImport::IsValidToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: b4dc1e60f3d29e2671882d1900a1c49e56969601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702864"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="1a07d-102">IMetaDataImport::IsValidToken 메서드</span><span class="sxs-lookup"><span data-stu-id="1a07d-102">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="1a07d-103">지정한 토큰이 코드 개체에 대한 유효한 참조를 포함하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1a07d-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a07d-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a07d-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a07d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1a07d-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="1a07d-106">진행 참조 유효성 검사에 사용할 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1a07d-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a07d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1a07d-107">Return Value</span></span>  

 <span data-ttu-id="1a07d-108">`true``tk`가 현재 범위 내의 유효한 메타 데이터 토큰 인 경우</span><span class="sxs-lookup"><span data-stu-id="1a07d-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="1a07d-109">그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="1a07d-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a07d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1a07d-110">Requirements</span></span>  

 <span data-ttu-id="1a07d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a07d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a07d-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1a07d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a07d-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a07d-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1a07d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a07d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a07d-115">참조</span><span class="sxs-lookup"><span data-stu-id="1a07d-115">See also</span></span>

- [<span data-ttu-id="1a07d-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a07d-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1a07d-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1a07d-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
