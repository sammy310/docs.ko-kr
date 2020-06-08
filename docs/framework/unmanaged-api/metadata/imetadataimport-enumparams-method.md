---
title: IMetaDataImport::EnumParams 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: f9a58a70b5264d7f1eb33fb0e09c702c94a13e85
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491769"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="8a3c5-102">IMetaDataImport::EnumParams 메서드</span><span class="sxs-lookup"><span data-stu-id="8a3c5-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="8a3c5-103">지정한 MethodDef 토큰이 참조하는 메서드의 매개 변수를 나타내는 ParamDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a3c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a3c5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a3c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a3c5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8a3c5-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8a3c5-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="8a3c5-108">진행 열거할 매개 변수가 있는 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="8a3c5-109">제한이 ParamDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8a3c5-110">[in] `rParams` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8a3c5-111">제한이 에서 반환 된 ParamDef 토큰의 수입니다 `rParams` .</span><span class="sxs-lookup"><span data-stu-id="8a3c5-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a3c5-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a3c5-112">Return Value</span></span>  
  
|<span data-ttu-id="8a3c5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a3c5-113">HRESULT</span></span>|<span data-ttu-id="8a3c5-114">설명</span><span class="sxs-lookup"><span data-stu-id="8a3c5-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a3c5-115">`EnumParams`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8a3c5-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="8a3c5-117">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a3c5-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a3c5-118">Requirements</span></span>  
 <span data-ttu-id="8a3c5-119">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3c5-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8a3c5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a3c5-121">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a3c5-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a3c5-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3c5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a3c5-123">See also</span></span>

- [<span data-ttu-id="8a3c5-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a3c5-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8a3c5-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a3c5-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
