---
title: IMetaDataImport::EnumTypeDefs 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20913d1cfa258036e8c20e826415f96a8984fdb4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103365"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="7d7da-102">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="7d7da-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="7d7da-103">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7da-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d7da-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d7da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d7da-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7d7da-106">[out] 새 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="7d7da-107">이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="7d7da-108">[in] TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7d7da-109">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="7d7da-110">[out] TypeDef 토큰에서 반환 된 수가 `rTypeDefs`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d7da-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d7da-111">Return Value</span></span>  
  
|<span data-ttu-id="7d7da-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d7da-112">HRESULT</span></span>|<span data-ttu-id="7d7da-113">설명</span><span class="sxs-lookup"><span data-stu-id="7d7da-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` <span data-ttu-id="7d7da-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7d7da-115">열거할 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7d7da-116">이런 경우 `pcTypeDefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d7da-117">설명</span><span class="sxs-lookup"><span data-stu-id="7d7da-117">Remarks</span></span>  
 <span data-ttu-id="7d7da-118">TypeDef 토큰에는 확장성 메커니즘을 통해 추가 된 모든 형식 뿐만 아니라 클래스 또는 인터페이스를 같은 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d7da-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d7da-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d7da-119">Requirements</span></span>  
 <span data-ttu-id="7d7da-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7d7da-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d7da-121">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7d7da-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d7da-122">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7d7da-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7d7da-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7d7da-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d7da-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d7da-124">See also</span></span>

- [<span data-ttu-id="7d7da-125">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d7da-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7d7da-126">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d7da-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
