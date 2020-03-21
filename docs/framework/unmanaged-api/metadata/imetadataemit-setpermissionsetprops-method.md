---
title: IMetaDataEmit::SetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177484"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="3937c-102">IMetaDataEmit::SetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3937c-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="3937c-103">[IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)에 대한 사전 호출에 의해 정의된 권한 집합의 메타데이터 서명 기능을 설정하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3937c-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3937c-104">구문</span><span class="sxs-lookup"><span data-stu-id="3937c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3937c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3937c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3937c-106">【인】 데코레이팅할 개체를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3937c-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="3937c-107">【인】 사용할 선언적 보안 유형을 지정하는 [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3937c-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="3937c-108">【인】 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="3937c-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="3937c-109">【인】 의 크기(바이트)입니다. `pvPermission`</span><span class="sxs-lookup"><span data-stu-id="3937c-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="3937c-110">【아웃】 업데이트된 `mdPermission` 사용 권한을 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3937c-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3937c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3937c-111">Requirements</span></span>  
 <span data-ttu-id="3937c-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3937c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3937c-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3937c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3937c-114">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3937c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3937c-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3937c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3937c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3937c-116">See also</span></span>

- [<span data-ttu-id="3937c-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3937c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3937c-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3937c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
