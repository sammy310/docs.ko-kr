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
ms.openlocfilehash: 3698525c139ed52b59ca577c598e675b6c26eef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719517"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="4ab5d-102">IMetaDataEmit::DefinePermissionSet 메서드</span><span class="sxs-lookup"><span data-stu-id="4ab5d-102">IMetaDataEmit::DefinePermissionSet Method</span></span>

<span data-ttu-id="4ab5d-103">지정 된 메타 데이터 시그니처를 사용 하 여 권한 집합에 대 한 정의를 만들고 해당 권한 집합 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ab5d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ab5d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ab5d-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="4ab5d-106">진행 데코레이팅 할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="4ab5d-107">진행 사용할 선언적 보안의 형식을 지정 하는 [CorDeclSecurity](cordeclsecurity-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="4ab5d-108">진행 권한 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="4ab5d-109">진행 의 크기 (바이트)입니다 `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="4ab5d-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="4ab5d-110">제한이 반환 된 권한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab5d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ab5d-111">Requirements</span></span>  

 <span data-ttu-id="4ab5d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab5d-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4ab5d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ab5d-114">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab5d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ab5d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab5d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab5d-116">참조</span><span class="sxs-lookup"><span data-stu-id="4ab5d-116">See also</span></span>

- [<span data-ttu-id="4ab5d-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ab5d-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4ab5d-118">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ab5d-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
