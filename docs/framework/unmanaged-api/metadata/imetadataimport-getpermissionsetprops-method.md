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
ms.openlocfilehash: 89c45c049ebadf9e1f16bef8d2626b4e2a17fb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729254"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="3810a-102">IMetaDataImport::GetPermissionSetProps 메서드</span><span class="sxs-lookup"><span data-stu-id="3810a-102">IMetaDataImport::GetPermissionSetProps Method</span></span>

<span data-ttu-id="3810a-103"><xref:System.Security.PermissionSet?displayProperty=nameWithType>지정 된 사용 권한 토큰이 나타내는와 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3810a-104">구문</span><span class="sxs-lookup"><span data-stu-id="3810a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3810a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3810a-105">Parameters</span></span>  

 `pm`  
 <span data-ttu-id="3810a-106">진행 메타 데이터 속성을 가져올 권한 집합을 나타내는 권한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="3810a-107">제한이 권한 집합에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="3810a-108">제한이 권한 집합의 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="3810a-109">제한이 의 크기 (바이트) `ppvPermission` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3810a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3810a-110">Requirements</span></span>  

 <span data-ttu-id="3810a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3810a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3810a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3810a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3810a-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3810a-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3810a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3810a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3810a-115">참조</span><span class="sxs-lookup"><span data-stu-id="3810a-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="3810a-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3810a-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3810a-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3810a-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
