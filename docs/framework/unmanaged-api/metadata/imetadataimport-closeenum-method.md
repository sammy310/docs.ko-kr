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
ms.openlocfilehash: f418b48f1b62ae8093197d64ca44b2ef659990a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701720"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="a4b16-102">IMetaDataImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="a4b16-102">IMetaDataImport::CloseEnum Method</span></span>

<span data-ttu-id="a4b16-103">지정 된 핸들로 식별 되는 열거자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b16-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b16-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4b16-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b16-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4b16-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="a4b16-106">진행 닫을 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a4b16-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b16-107">설명</span><span class="sxs-lookup"><span data-stu-id="a4b16-107">Remarks</span></span>  

 <span data-ttu-id="a4b16-108">로 지정 된 핸들은 `hEnum` 이전 `Enum` *이름* 호출에서 가져옵니다 (예 [: IMetaDataImport:: enumtypedefs](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a4b16-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b16-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4b16-109">Requirements</span></span>  

 <span data-ttu-id="a4b16-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4b16-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b16-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a4b16-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4b16-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4b16-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4b16-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b16-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b16-114">참조</span><span class="sxs-lookup"><span data-stu-id="a4b16-114">See also</span></span>

- [<span data-ttu-id="a4b16-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b16-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a4b16-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4b16-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
