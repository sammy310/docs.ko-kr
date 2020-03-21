---
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
ms.openlocfilehash: e02d7dd4b287d027b633ae9bf2e98e036062bdd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175410"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="d2086-102">IMetaDataImport::GetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="d2086-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="d2086-103">지정한 TypeDef 토큰이 참조하는 클래스에 대한 레이아웃 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2086-104">구문</span><span class="sxs-lookup"><span data-stu-id="d2086-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d2086-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d2086-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d2086-106">【인】 반환할 레이아웃이 있는 클래스에 대한 TypeDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="d2086-107">【아웃】 클래스의 팩 크기를 나타내는 값 1, 2, 4, 8 또는 16 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="d2086-108">【아웃】 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d2086-109">[in] `rFieldOffset` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="d2086-110">【아웃】 에서 반환되는 요소 `rFieldOffset`의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2086-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="d2086-111">【아웃】 로 표시되는 클래스의 바이트 크기입니다. `td`</span><span class="sxs-lookup"><span data-stu-id="d2086-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2086-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d2086-112">Requirements</span></span>  
 <span data-ttu-id="d2086-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2086-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2086-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="d2086-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2086-115">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d2086-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2086-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2086-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2086-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2086-117">See also</span></span>

- [<span data-ttu-id="d2086-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2086-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d2086-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d2086-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
