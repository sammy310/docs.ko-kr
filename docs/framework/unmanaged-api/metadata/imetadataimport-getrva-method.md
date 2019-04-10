---
title: IMetaDataImport::GetRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96c013cd3e45e4ede0cbc9f42bf511a2eb3fc12d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223591"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="6ea80-102">IMetaDataImport::GetRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="6ea80-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="6ea80-103">상대 가상 주소 (RVA) 및 메서드 또는 지정한 토큰이 나타내는 필드의 구현 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea80-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ea80-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ea80-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6ea80-106">[in] MethodDef 또는 FieldDef 메타 데이터 토큰에 대 한 RVA 반환할 코드 개체를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="6ea80-107">한 FieldDef 토큰을 사용 하는 경우 필드에는 전역 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="6ea80-108">[out] 토큰이 나타내는 코드 개체의 상대 가상 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="6ea80-109">[out] 메서드에 대 한 구현 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="6ea80-110">이 값은의 비트 마스크를 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="6ea80-111">변수의 `pdwImplFlags` 유효한 경우에만 `tk` MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea80-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea80-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ea80-112">Requirements</span></span>  
 <span data-ttu-id="6ea80-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6ea80-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea80-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6ea80-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ea80-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6ea80-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ea80-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="6ea80-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea80-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ea80-117">See also</span></span>

- [<span data-ttu-id="6ea80-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ea80-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6ea80-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ea80-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
