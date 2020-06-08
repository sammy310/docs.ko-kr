---
title: IMetaDataImport::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: 5de62db4180a6a9160193053fe42e39cebc34d0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492495"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="6132e-102">IMetaDataImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="6132e-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="6132e-103">지정 된 핸들로 식별 되는 열거자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6132e-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6132e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6132e-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6132e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6132e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6132e-106">진행 닫을 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="6132e-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6132e-107">설명</span><span class="sxs-lookup"><span data-stu-id="6132e-107">Remarks</span></span>  
 <span data-ttu-id="6132e-108">로 지정 된 핸들은 `hEnum` 이전 `Enum` *이름* 호출에서 가져옵니다 (예 [: IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="6132e-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6132e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6132e-109">Requirements</span></span>  
 <span data-ttu-id="6132e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6132e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6132e-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6132e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6132e-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6132e-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6132e-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6132e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6132e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6132e-114">See also</span></span>

- [<span data-ttu-id="6132e-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6132e-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6132e-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6132e-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
