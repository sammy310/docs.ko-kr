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
ms.openlocfilehash: b780ca513d8a0b4f88e66594e86e9ff8290f6523
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177358"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="7edbf-102">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="7edbf-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="7edbf-103">지정된 열거형에서 검색된 열거형의 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7edbf-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7edbf-104">구문</span><span class="sxs-lookup"><span data-stu-id="7edbf-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7edbf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7edbf-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="7edbf-106">【인】 열거자의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7edbf-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="7edbf-107">【아웃】 열거된 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7edbf-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7edbf-108">설명</span><span class="sxs-lookup"><span data-stu-id="7edbf-108">Remarks</span></span>  
 <span data-ttu-id="7edbf-109">지정된 `hEnum` 핸들은 이전 `Enum` *이름* 호출(예: [IMetaDataImport::EnumTypeDefs)에서](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7edbf-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7edbf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7edbf-110">Requirements</span></span>  
 <span data-ttu-id="7edbf-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7edbf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7edbf-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="7edbf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7edbf-113">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7edbf-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7edbf-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7edbf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edbf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7edbf-115">See also</span></span>

- [<span data-ttu-id="7edbf-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7edbf-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7edbf-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7edbf-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
