---
title: IMetaDataImport::CountEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f657957d42cef1421ab3aa19f297bd04b0cacd8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781326"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="043ae-102">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="043ae-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="043ae-103">지정된 된 열거자에서 검색 된 열거형의 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="043ae-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="043ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="043ae-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="043ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="043ae-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="043ae-106">[in] 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="043ae-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="043ae-107">[out] 열거 된 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="043ae-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="043ae-108">설명</span><span class="sxs-lookup"><span data-stu-id="043ae-108">Remarks</span></span>  
 <span data-ttu-id="043ae-109">지정 된 핸들 `hEnum` 이전에서 가져온 `Enum` *이름* 호출 (예를 들어 [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="043ae-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="043ae-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="043ae-110">Requirements</span></span>  
 <span data-ttu-id="043ae-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="043ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="043ae-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="043ae-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="043ae-113">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="043ae-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="043ae-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="043ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043ae-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="043ae-115">See also</span></span>

- [<span data-ttu-id="043ae-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="043ae-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="043ae-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="043ae-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
