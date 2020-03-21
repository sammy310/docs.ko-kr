---
title: IMetaDataImport::GetPermissionSetProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175345"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="99eae-102">IMetaDataImport::GetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="99eae-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="99eae-103">지정된 권한 토큰으로 <xref:System.Security.PermissionSet?displayProperty=nameWithType> 표시되는 메타데이터와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99eae-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99eae-104">구문</span><span class="sxs-lookup"><span data-stu-id="99eae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99eae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99eae-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="99eae-106">【인】 메타데이터 속성을 가져오는 권한 집합을 나타내는 권한 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="99eae-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="99eae-107">【아웃】 사용 권한 집합에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99eae-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="99eae-108">【아웃】 사용 권한 집합의 이진 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99eae-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="99eae-109">【아웃】 의 바이트 크기입니다. `ppvPermission`</span><span class="sxs-lookup"><span data-stu-id="99eae-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99eae-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99eae-110">Requirements</span></span>  
 <span data-ttu-id="99eae-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99eae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99eae-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="99eae-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99eae-113">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99eae-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99eae-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99eae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99eae-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99eae-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="99eae-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99eae-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="99eae-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99eae-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
