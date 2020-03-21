---
title: IMetaDataEmit::DefinePermissionSet 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175800"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="458ec-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="458ec-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="458ec-103">지정된 메타데이터 시그니처를 사용하여 권한 집합에 대한 정의를 만들고 해당 권한 집합 정의에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="458ec-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="458ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="458ec-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="458ec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="458ec-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="458ec-106">【인】 장식할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="458ec-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="458ec-107">【인】 사용할 선언적 보안 유형을 지정하는 [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="458ec-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="458ec-108">【인】 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="458ec-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="458ec-109">【인】 의 크기(바이트)입니다. `pvPermission`</span><span class="sxs-lookup"><span data-stu-id="458ec-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="458ec-110">【아웃】 반환된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="458ec-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="458ec-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="458ec-111">Requirements</span></span>  
 <span data-ttu-id="458ec-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="458ec-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="458ec-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="458ec-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="458ec-114">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="458ec-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="458ec-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="458ec-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="458ec-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="458ec-116">See also</span></span>

- [<span data-ttu-id="458ec-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="458ec-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="458ec-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="458ec-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
