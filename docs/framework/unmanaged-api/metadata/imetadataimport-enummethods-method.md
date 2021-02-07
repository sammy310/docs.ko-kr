---
description: 'IMetaDataImport:: EnumMethods 메서드에 대해 자세히 알아보세요.'
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
ms.openlocfilehash: 4fce3593d088a8d401335869eb49e598ac4c3fd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670680"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="5ef88-103">IMetaDataImport::EnumMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="5ef88-103">IMetaDataImport::EnumMethods Method</span></span>

<span data-ttu-id="5ef88-104">지정한 형식의 메서드를 나타내는 MethodDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-104">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef88-105">구문</span><span class="sxs-lookup"><span data-stu-id="5ef88-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef88-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ef88-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="5ef88-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5ef88-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-108">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="5ef88-109">진행 열거할 메서드가 포함 된 형식을 나타내는 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-109">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="5ef88-110">제한이 MethodDef 토큰을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-110">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ef88-111">진행 MethodDef 배열의 최대 크기 `rMethods` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-111">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5ef88-112">제한이 에서 반환 된 MethodDef 토큰의 수입니다 `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="5ef88-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef88-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="5ef88-113">Return Value</span></span>  
  
|<span data-ttu-id="5ef88-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ef88-114">HRESULT</span></span>|<span data-ttu-id="5ef88-115">설명</span><span class="sxs-lookup"><span data-stu-id="5ef88-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5ef88-116">`EnumMethods` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-116">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5ef88-117">열거할 MethodDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-117">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="5ef88-118">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ef88-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ef88-119">Requirements</span></span>  

 <span data-ttu-id="5ef88-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ef88-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef88-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5ef88-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ef88-122">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ef88-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ef88-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef88-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef88-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ef88-124">See also</span></span>

- [<span data-ttu-id="5ef88-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ef88-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5ef88-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ef88-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
