---
description: '자세히 알아보기: IMetaDataImport:: GetClassLayout 메서드'
title: IMetaDataImport::GetClassLayout 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 74a3170e40a7f857b9150f2d0048af3eac0f2cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745426"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="4f846-103">IMetaDataImport::GetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="4f846-103">IMetaDataImport::GetClassLayout Method</span></span>

<span data-ttu-id="4f846-104">지정한 TypeDef 토큰이 참조하는 클래스에 대한 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-104">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f846-105">구문</span><span class="sxs-lookup"><span data-stu-id="4f846-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f846-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f846-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="4f846-107">진행 반환할 레이아웃이 포함 된 클래스에 대 한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-107">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="4f846-108">제한이 클래스의 팩 크기를 나타내는 값 1, 2, 4, 8 또는 16 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-108">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="4f846-109">제한이 [COR_FIELD_OFFSET](cor-field-offset-structure.md) 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-109">[out] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4f846-110">[in] `rFieldOffset` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-110">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="4f846-111">제한이 에서 반환 된 요소의 수 `rFieldOffset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-111">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="4f846-112">제한이 가 나타내는 클래스의 크기 (바이트)입니다 `td` .</span><span class="sxs-lookup"><span data-stu-id="4f846-112">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f846-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f846-113">Requirements</span></span>  

 <span data-ttu-id="4f846-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f846-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f846-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4f846-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f846-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f846-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f846-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f846-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f846-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f846-118">See also</span></span>

- [<span data-ttu-id="4f846-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f846-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4f846-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f846-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
