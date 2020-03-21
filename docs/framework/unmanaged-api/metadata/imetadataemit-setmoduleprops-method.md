---
title: IMetaDataEmit::SetModuleProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175618"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="f1bee-102">IMetaDataEmit::SetModuleProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f1bee-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="f1bee-103">업데이트는 [IMetaDataEmit::DefineModuleRef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)대한 사전 호출에 의해 정의된 모듈에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bee-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1bee-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1bee-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1bee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1bee-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f1bee-106">【인】 유니코드의 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bee-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="f1bee-107">이 이름은 파일 이름일 뿐 전체 경로 이름은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f1bee-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1bee-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1bee-108">Requirements</span></span>  
 <span data-ttu-id="f1bee-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1bee-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1bee-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="f1bee-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1bee-111">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="f1bee-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1bee-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1bee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bee-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1bee-113">See also</span></span>

- [<span data-ttu-id="f1bee-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1bee-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1bee-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1bee-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
