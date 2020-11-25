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
ms.openlocfilehash: f2470cd7112adff35ef49c21a155072fcd4008be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727291"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="2a048-102">IMetaDataImport::CountEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="2a048-102">IMetaDataImport::CountEnum Method</span></span>

<span data-ttu-id="2a048-103">지정 된 열거자에 의해 검색 된 열거형의 요소 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a048-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a048-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a048-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a048-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a048-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="2a048-106">진행 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="2a048-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="2a048-107">제한이 열거 된 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a048-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a048-108">설명</span><span class="sxs-lookup"><span data-stu-id="2a048-108">Remarks</span></span>  

 <span data-ttu-id="2a048-109">로 지정 된 핸들은 `hEnum` 이전 `Enum` *이름* 호출에서 가져옵니다 (예 [: IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="2a048-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a048-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a048-110">Requirements</span></span>  

 <span data-ttu-id="2a048-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a048-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a048-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2a048-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a048-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a048-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a048-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a048-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a048-115">참조</span><span class="sxs-lookup"><span data-stu-id="2a048-115">See also</span></span>

- [<span data-ttu-id="2a048-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a048-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2a048-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a048-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
