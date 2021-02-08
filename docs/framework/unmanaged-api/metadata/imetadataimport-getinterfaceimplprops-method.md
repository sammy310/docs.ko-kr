---
description: '자세히 알아보기: IMetaDataImport:: GetInterfaceImplProps 메서드'
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
ms.openlocfilehash: 6b3c9394bcf37f700c84e1fda0b785dc0c3f4713
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783913"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="90604-103">IMetaDataImport::GetInterfaceImplProps 메서드</span><span class="sxs-lookup"><span data-stu-id="90604-103">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="90604-104"><xref:System.Type>지정 된 메서드를 구현 하는 및 해당 메서드를 선언 하는 인터페이스에 대 한 메타 데이터 토큰에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90604-104">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="90604-105">구문</span><span class="sxs-lookup"><span data-stu-id="90604-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90604-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90604-106">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="90604-107">진행 클래스 및 인터페이스 토큰을 반환할 메서드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90604-107">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="90604-108">제한이 메서드를 구현 하는 클래스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90604-108">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="90604-109">제한이 구현 된 메서드를 정의 하는 인터페이스를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="90604-109">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="90604-110">설명</span><span class="sxs-lookup"><span data-stu-id="90604-110">Remarks</span></span>

 <span data-ttu-id="90604-111">`iImpl` [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 메서드를 호출 하 여의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90604-111">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="90604-112">예를 들어, 클래스의 `mdTypeDef` 토큰 값이 0x02000007이 고 형식에 토큰이 있는 세 개의 인터페이스를 구현 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90604-112">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="90604-113">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="90604-113">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="90604-114">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="90604-114">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="90604-115">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="90604-115">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="90604-116">개념적으로이 정보는 다음과 같이 인터페이스 구현 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90604-116">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="90604-117">행 번호</span><span class="sxs-lookup"><span data-stu-id="90604-117">Row number</span></span> | <span data-ttu-id="90604-118">클래스 토큰</span><span class="sxs-lookup"><span data-stu-id="90604-118">Class token</span></span> | <span data-ttu-id="90604-119">인터페이스 토큰</span><span class="sxs-lookup"><span data-stu-id="90604-119">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="90604-120">4</span><span class="sxs-lookup"><span data-stu-id="90604-120">4</span></span>          |             |                 |
| <span data-ttu-id="90604-121">5</span><span class="sxs-lookup"><span data-stu-id="90604-121">5</span></span>          | <span data-ttu-id="90604-122">02000007</span><span class="sxs-lookup"><span data-stu-id="90604-122">02000007</span></span>    | <span data-ttu-id="90604-123">02000003</span><span class="sxs-lookup"><span data-stu-id="90604-123">02000003</span></span>        |
| <span data-ttu-id="90604-124">6</span><span class="sxs-lookup"><span data-stu-id="90604-124">6</span></span>          | <span data-ttu-id="90604-125">02000007</span><span class="sxs-lookup"><span data-stu-id="90604-125">02000007</span></span>    | <span data-ttu-id="90604-126">0100000A</span><span class="sxs-lookup"><span data-stu-id="90604-126">0100000A</span></span>        |
| <span data-ttu-id="90604-127">7</span><span class="sxs-lookup"><span data-stu-id="90604-127">7</span></span>          |             |                 |
| <span data-ttu-id="90604-128">8</span><span class="sxs-lookup"><span data-stu-id="90604-128">8</span></span>          | <span data-ttu-id="90604-129">02000007</span><span class="sxs-lookup"><span data-stu-id="90604-129">02000007</span></span>    | <span data-ttu-id="90604-130">0200001C</span><span class="sxs-lookup"><span data-stu-id="90604-130">0200001C</span></span>        |

<span data-ttu-id="90604-131">리콜, 토큰은 4 바이트 값입니다.</span><span class="sxs-lookup"><span data-stu-id="90604-131">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="90604-132">하위 3 바이트는 행 번호 또는 RID를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="90604-132">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="90604-133">상위 바이트는 토큰 유형 – 0x09를 보유 `mdtInterfaceImpl` 합니다.</span><span class="sxs-lookup"><span data-stu-id="90604-133">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="90604-134">`GetInterfaceImplProps` 인수에 제공 하는 토큰을 포함 하는 행에 저장 된 정보를 반환 합니다 `iImpl` .</span><span class="sxs-lookup"><span data-stu-id="90604-134">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="90604-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90604-135">Requirements</span></span>  

 <span data-ttu-id="90604-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90604-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90604-137">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="90604-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90604-138">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90604-138">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90604-139">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90604-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90604-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90604-140">See also</span></span>

- [<span data-ttu-id="90604-141">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90604-141">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="90604-142">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90604-142">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
