---
title: IMetaDataEmit::SetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
ms.openlocfilehash: d0066c6590a9e0cf278e036111c2739f7cfaf679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003908"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="1350e-102">IMetaDataEmit::SetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="1350e-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="1350e-103">지정 된 토큰이 참조 하는 필드, 메서드 반환 또는 메서드 매개 변수에 대 한 PInvoke 마샬링 정보를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1350e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1350e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1350e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1350e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1350e-106">진행 대상 데이터 항목에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-106">[in] The token for target data item.</span></span> <span data-ttu-id="1350e-107">`mdFieldDef`또는 `mdParamDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="1350e-108">진행 관리 되지 않는 형식에 대 한 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="1350e-109">진행 의 바이트 수 `pvNativeType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1350e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1350e-110">Requirements</span></span>  
 <span data-ttu-id="1350e-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1350e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1350e-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1350e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1350e-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1350e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1350e-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1350e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1350e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1350e-115">See also</span></span>

- [<span data-ttu-id="1350e-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1350e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1350e-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1350e-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
