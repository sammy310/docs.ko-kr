---
description: '자세한 정보: IMetaDataEmit:: Set Setprops 메서드'
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
ms.openlocfilehash: 1e2786a21a1024f32328e36878a1a2427af54f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771888"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="18e65-103">IMetaDataEmit::SetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="18e65-103">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="18e65-104">[IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md)에 대 한 이전 호출로 정의 된 사용 권한 집합의 메타 데이터 서명 기능을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-104">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e65-105">구문</span><span class="sxs-lookup"><span data-stu-id="18e65-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18e65-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18e65-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="18e65-107">진행 데코레이팅 할 개체를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-107">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="18e65-108">진행 사용할 선언적 보안의 형식을 지정 하는 [CorDeclSecurity](cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-108">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="18e65-109">진행 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-109">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="18e65-110">진행 의 크기 (바이트)입니다 `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="18e65-110">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="18e65-111">제한이 `mdPermission` 업데이트 된 사용 권한을 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-111">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18e65-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18e65-112">Requirements</span></span>  

 <span data-ttu-id="18e65-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18e65-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18e65-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="18e65-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18e65-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18e65-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18e65-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18e65-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e65-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18e65-117">See also</span></span>

- [<span data-ttu-id="18e65-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18e65-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="18e65-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18e65-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
