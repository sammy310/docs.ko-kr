---
description: '자세히 알아보기: IMetaDataImport:: EnumTypeDefs 메서드'
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
ms.openlocfilehash: 28bd06b70573b780b687da9de0e13e17c29bb39a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670684"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="4875a-103">IMetaDataImport::EnumTypeDefs 메서드</span><span class="sxs-lookup"><span data-stu-id="4875a-103">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="4875a-104">현재 범위 내의 모든 형식을 나타내는 TypeDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-104">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4875a-105">구문</span><span class="sxs-lookup"><span data-stu-id="4875a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4875a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4875a-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4875a-107">제한이 새 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-107">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="4875a-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-108">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="4875a-109">진행 TypeDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-109">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4875a-110">[in] `rTypeDefs` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-110">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="4875a-111">제한이 에서 반환 된 TypeDef 토큰의 수입니다 `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="4875a-111">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4875a-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="4875a-112">Return Value</span></span>  
  
|<span data-ttu-id="4875a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4875a-113">HRESULT</span></span>|<span data-ttu-id="4875a-114">설명</span><span class="sxs-lookup"><span data-stu-id="4875a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4875a-115">`EnumTypeDefs` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-115">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4875a-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="4875a-117">이 경우는 `pcTypeDefs` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-117">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4875a-118">설명</span><span class="sxs-lookup"><span data-stu-id="4875a-118">Remarks</span></span>  

 <span data-ttu-id="4875a-119">TypeDef 토큰은 클래스 또는 인터페이스와 같은 형식 뿐만 아니라 확장성 메커니즘을 통해 추가 된 모든 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-119">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4875a-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4875a-120">Requirements</span></span>  

 <span data-ttu-id="4875a-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4875a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4875a-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4875a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4875a-123">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4875a-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4875a-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4875a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4875a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4875a-125">See also</span></span>

- [<span data-ttu-id="4875a-126">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4875a-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4875a-127">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4875a-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
