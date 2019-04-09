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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7846eeceeb4d59c4e9aae73c79172c89184396e0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123871"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="0255c-102">IMetaDataImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="0255c-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="0255c-103">지정 된 핸들에 의해 식별 되는 열거자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0255c-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0255c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0255c-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0255c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0255c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="0255c-106">[in] 닫으려면 열거자에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="0255c-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0255c-107">설명</span><span class="sxs-lookup"><span data-stu-id="0255c-107">Remarks</span></span>  
 <span data-ttu-id="0255c-108">지정 된 핸들 `hEnum` 이전에서 가져온 `Enum` *이름* 호출 (예를 들어 [imetadataimport:: Enumtypedefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="0255c-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0255c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0255c-109">Requirements</span></span>  
 <span data-ttu-id="0255c-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0255c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0255c-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0255c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0255c-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0255c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0255c-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="0255c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0255c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0255c-114">See also</span></span>

- [<span data-ttu-id="0255c-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0255c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0255c-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0255c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
