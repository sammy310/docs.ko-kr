---
title: IMetaDataImport::EnumMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177303"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="694e9-102">IMetaDataImport::EnumMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="694e9-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="694e9-103">지정한 형식의 메서드를 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="694e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="694e9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="694e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="694e9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="694e9-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="694e9-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야합니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="694e9-108">【인】 개율할 메서드를 사용하여 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="694e9-109">【아웃】 MethodDef 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="694e9-110">【인】 MethodDef `rMethods` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="694e9-111">【아웃】 에서 반환되는 MethodDef 토큰 `rMethods`수입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="694e9-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="694e9-112">Return Value</span></span>  
  
|<span data-ttu-id="694e9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="694e9-113">HRESULT</span></span>|<span data-ttu-id="694e9-114">Description</span><span class="sxs-lookup"><span data-stu-id="694e9-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="694e9-115">`EnumMethods`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="694e9-116">메서드Def 를 등록할 수 있는 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="694e9-117">이 경우 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="694e9-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="694e9-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="694e9-118">Requirements</span></span>  
 <span data-ttu-id="694e9-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="694e9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="694e9-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="694e9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="694e9-121">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="694e9-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="694e9-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="694e9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694e9-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="694e9-123">See also</span></span>

- [<span data-ttu-id="694e9-124">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="694e9-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="694e9-125">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="694e9-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
