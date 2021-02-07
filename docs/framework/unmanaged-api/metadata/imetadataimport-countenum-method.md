---
description: '자세히 알아보기: IMetaDataImport:: CountEnum 메서드'
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
ms.openlocfilehash: c579ef7ce440e3552ab28572fc6c96ad12d66400
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677693"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="9ee2a-103">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="9ee2a-103">IMetaDataImport::CountEnum Method</span></span>

<span data-ttu-id="9ee2a-104">지정 된 열거자에 의해 검색 된 열거형의 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ee2a-104">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="9ee2a-105">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ee2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ee2a-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="9ee2a-107">진행 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee2a-107">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="9ee2a-108">제한이 열거 된 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee2a-108">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ee2a-109">설명</span><span class="sxs-lookup"><span data-stu-id="9ee2a-109">Remarks</span></span>  

 <span data-ttu-id="9ee2a-110">로 지정 된 핸들은 `hEnum` 이전 `Enum` *이름* 호출에서 가져옵니다 (예 [: IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="9ee2a-110">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee2a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ee2a-111">Requirements</span></span>  

 <span data-ttu-id="9ee2a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ee2a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee2a-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9ee2a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ee2a-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ee2a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee2a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee2a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ee2a-116">See also</span></span>

- [<span data-ttu-id="9ee2a-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ee2a-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="9ee2a-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ee2a-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
