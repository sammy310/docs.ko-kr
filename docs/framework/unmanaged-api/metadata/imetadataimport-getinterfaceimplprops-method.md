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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175384"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="73f7c-102">IMetaDataImport::GetInterfaceImplProps 메서드</span><span class="sxs-lookup"><span data-stu-id="73f7c-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="73f7c-103">지정된 메서드를 구현하는 <xref:System.Type> 메서드와 해당 메서드를 선언하는 인터페이스에 대한 메타데이터 토큰에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="73f7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="73f7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73f7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="73f7c-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="73f7c-106">【인】 클래스 및 인터페이스 토큰을 반환하는 메서드를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="73f7c-107">【아웃】 메서드를 구현하는 클래스를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="73f7c-108">【아웃】 구현된 메서드를 정의하는 인터페이스를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="73f7c-109">설명</span><span class="sxs-lookup"><span data-stu-id="73f7c-109">Remarks</span></span>

 <span data-ttu-id="73f7c-110">`iImpl` [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드를 호출 하 여 대 한 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="73f7c-111">예를 들어 클래스에 `mdTypeDef` 토큰 값이 0x0200007이고 형식에 토큰이 있는 세 개의 인터페이스를 구현한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="73f7c-112">0x020000003(TypeDef)</span><span class="sxs-lookup"><span data-stu-id="73f7c-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="73f7c-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="73f7c-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="73f7c-114">0x0200001C(TypeDef)</span><span class="sxs-lookup"><span data-stu-id="73f7c-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="73f7c-115">개념적으로 이 정보는 다음과 같이 인터페이스 구현 테이블에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="73f7c-116">행 번호</span><span class="sxs-lookup"><span data-stu-id="73f7c-116">Row number</span></span> | <span data-ttu-id="73f7c-117">클래스 토큰</span><span class="sxs-lookup"><span data-stu-id="73f7c-117">Class token</span></span> | <span data-ttu-id="73f7c-118">인터페이스 토큰</span><span class="sxs-lookup"><span data-stu-id="73f7c-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="73f7c-119">4</span><span class="sxs-lookup"><span data-stu-id="73f7c-119">4</span></span>          |             |                 |
| <span data-ttu-id="73f7c-120">5</span><span class="sxs-lookup"><span data-stu-id="73f7c-120">5</span></span>          | <span data-ttu-id="73f7c-121">02000007</span><span class="sxs-lookup"><span data-stu-id="73f7c-121">02000007</span></span>    | <span data-ttu-id="73f7c-122">02000003</span><span class="sxs-lookup"><span data-stu-id="73f7c-122">02000003</span></span>        |
| <span data-ttu-id="73f7c-123">6</span><span class="sxs-lookup"><span data-stu-id="73f7c-123">6</span></span>          | <span data-ttu-id="73f7c-124">02000007</span><span class="sxs-lookup"><span data-stu-id="73f7c-124">02000007</span></span>    | <span data-ttu-id="73f7c-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="73f7c-125">0100000A</span></span>        |
| <span data-ttu-id="73f7c-126">7</span><span class="sxs-lookup"><span data-stu-id="73f7c-126">7</span></span>          |             |                 |
| <span data-ttu-id="73f7c-127">8</span><span class="sxs-lookup"><span data-stu-id="73f7c-127">8</span></span>          | <span data-ttu-id="73f7c-128">02000007</span><span class="sxs-lookup"><span data-stu-id="73f7c-128">02000007</span></span>    | <span data-ttu-id="73f7c-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="73f7c-129">0200001C</span></span>        |

<span data-ttu-id="73f7c-130">토큰은 4바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="73f7c-131">3바이트가 낮을수록 행 번호 또는 RID가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="73f7c-132">위쪽 바이트는 토큰 형식인 0x09를 보유합니다. `mdtInterfaceImpl`</span><span class="sxs-lookup"><span data-stu-id="73f7c-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="73f7c-133">`GetInterfaceImplProps`은 인수에서 제공하는 토큰행에 있는 `iImpl` 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="73f7c-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="73f7c-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73f7c-134">Requirements</span></span>  
 <span data-ttu-id="73f7c-135">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73f7c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f7c-136">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="73f7c-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73f7c-137">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="73f7c-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73f7c-138">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f7c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f7c-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73f7c-139">See also</span></span>

- [<span data-ttu-id="73f7c-140">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73f7c-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="73f7c-141">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73f7c-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
