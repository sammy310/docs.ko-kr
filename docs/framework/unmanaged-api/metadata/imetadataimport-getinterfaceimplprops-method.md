---
title: IMetaDataImport::GetInterfaceImplProps 메서드
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115936"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="63350-102">IMetaDataImport::GetInterfaceImplProps 메서드</span><span class="sxs-lookup"><span data-stu-id="63350-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="63350-103">에 대 한 메타 데이터 토큰에 대 한 포인터를 가져옵니다는 <xref:System.Type> 지정된 된 메서드를 구현 하 고 해당 메서드를 선언 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="63350-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="63350-104">구문</span><span class="sxs-lookup"><span data-stu-id="63350-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63350-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="63350-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="63350-106">[in] 에 대 한 클래스 및 인터페이스 토큰을 반환 하는 메서드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="63350-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="63350-107">[out] 메서드를 구현 하는 클래스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="63350-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="63350-108">[out] 구현 된 메서드를 정의 하는 인터페이스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="63350-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="63350-109">설명</span><span class="sxs-lookup"><span data-stu-id="63350-109">Remarks</span></span>

 <span data-ttu-id="63350-110">값을 가져옵니다 `iImpl` 를 호출 하 여 합니다 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="63350-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="63350-111">예를 들어, 클래스에는 `mdTypeDef` 이 0x02000007 값 및 해당 형식 토큰에는 세 가지 인터페이스를 구현 함을 토큰:</span><span class="sxs-lookup"><span data-stu-id="63350-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="63350-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="63350-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="63350-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="63350-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="63350-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="63350-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="63350-115">개념적으로이 정보는으로 인터페이스 구현 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63350-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="63350-116">행 번호</span><span class="sxs-lookup"><span data-stu-id="63350-116">Row number</span></span> | <span data-ttu-id="63350-117">토큰 클래스</span><span class="sxs-lookup"><span data-stu-id="63350-117">Class token</span></span> | <span data-ttu-id="63350-118">토큰 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63350-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="63350-119">4</span><span class="sxs-lookup"><span data-stu-id="63350-119">4</span></span>          |             |                 |
| <span data-ttu-id="63350-120">5</span><span class="sxs-lookup"><span data-stu-id="63350-120">5</span></span>          | <span data-ttu-id="63350-121">02000007</span><span class="sxs-lookup"><span data-stu-id="63350-121">02000007</span></span>    | <span data-ttu-id="63350-122">02000003</span><span class="sxs-lookup"><span data-stu-id="63350-122">02000003</span></span>        |
| <span data-ttu-id="63350-123">6</span><span class="sxs-lookup"><span data-stu-id="63350-123">6</span></span>          | <span data-ttu-id="63350-124">02000007</span><span class="sxs-lookup"><span data-stu-id="63350-124">02000007</span></span>    | <span data-ttu-id="63350-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="63350-125">0100000A</span></span>        |
| <span data-ttu-id="63350-126">7</span><span class="sxs-lookup"><span data-stu-id="63350-126">7</span></span>          |             |                 |
| <span data-ttu-id="63350-127">8</span><span class="sxs-lookup"><span data-stu-id="63350-127">8</span></span>          | <span data-ttu-id="63350-128">02000007</span><span class="sxs-lookup"><span data-stu-id="63350-128">02000007</span></span>    | <span data-ttu-id="63350-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="63350-129">0200001C</span></span>        |

<span data-ttu-id="63350-130">회수 토큰은 4 바이트 값:</span><span class="sxs-lookup"><span data-stu-id="63350-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="63350-131">하위 3 바이트 행 수를 보유 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="63350-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="63350-132">토큰 유형이 – 0x09를 보유 하는 상위 바이트 `mdtInterfaceImpl`합니다.</span><span class="sxs-lookup"><span data-stu-id="63350-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

`GetInterfaceImplProps` <span data-ttu-id="63350-133">행에 제공한 토큰이에 저장 된 정보를 반환 합니다 `iImpl` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="63350-133">returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="63350-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63350-134">Requirements</span></span>  
 <span data-ttu-id="63350-135">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="63350-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63350-136">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63350-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63350-137">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="63350-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="63350-138">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="63350-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63350-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="63350-139">See also</span></span>

- [<span data-ttu-id="63350-140">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63350-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="63350-141">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="63350-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
