---
title: IMetaDataEmit::DefinePinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
ms.openlocfilehash: b46d39ab3958227c1fca24ceb3a9934f2778aa2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719504"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="6e500-102">IMetaDataEmit::DefinePinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="6e500-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>

<span data-ttu-id="6e500-103">지정 된 토큰이 참조 하는 메서드에 대 한 PInvoke 시그니처의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e500-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e500-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (
    [in]  mdToken            tk,
    [in]  DWORD              dwMappingFlags,
    [in]  LPCWSTR            szImportName,
    [in]  mdModuleRef        mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e500-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e500-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="6e500-106">진행 대상 메서드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="6e500-107">진행 PInvoke에서 매핑을 수행 하는 데 사용 되는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="6e500-108">진행 관리 되지 않는 DLL의 대상 내보내기 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="6e500-109">진행 대상 네이티브 DLL의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e500-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e500-110">Requirements</span></span>  

 <span data-ttu-id="6e500-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e500-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e500-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6e500-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e500-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e500-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e500-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e500-115">참조</span><span class="sxs-lookup"><span data-stu-id="6e500-115">See also</span></span>

- [<span data-ttu-id="6e500-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e500-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6e500-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e500-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
