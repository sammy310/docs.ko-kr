---
title: IAssemblyCache::InstallAssembly 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.InstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::InstallAssembly
helpviewer_keywords:
- InstallAssembly method [.NET Framework fusion]
- IAssemblyCache::InstallAssembly method [.NET Framework fusion]
ms.assetid: 33c1d269-c85e-4cb1-b0e6-1c510c8fb5fa
topic_type:
- apiref
ms.openlocfilehash: ec08c786992996ec6f44038ff3c1596cada88484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127078"
---
# <a name="iassemblycacheinstallassembly-method"></a><span data-ttu-id="eca2a-102">IAssemblyCache::InstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="eca2a-102">IAssemblyCache::InstallAssembly Method</span></span>
<span data-ttu-id="eca2a-103">지정 된 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="eca2a-103">Installs the specified assembly in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca2a-104">구문</span><span class="sxs-lookup"><span data-stu-id="eca2a-104">Syntax</span></span>  
  
```cpp  
HRESULT InstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszManifestFilePath,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eca2a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eca2a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="eca2a-106">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="eca2a-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="eca2a-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eca2a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="eca2a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="eca2a-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="eca2a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="eca2a-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pszManifestFilePath`  
 <span data-ttu-id="eca2a-110">진행 설치할 어셈블리의 매니페스트에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="eca2a-110">[in] The path to the manifest for the assembly to install.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="eca2a-111">진행 설치에 대 한 데이터를 포함 하는 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="eca2a-111">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains data for the installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eca2a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eca2a-112">Requirements</span></span>  
 <span data-ttu-id="eca2a-113">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eca2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eca2a-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="eca2a-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eca2a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eca2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca2a-116">참조</span><span class="sxs-lookup"><span data-stu-id="eca2a-116">See also</span></span>

- [<span data-ttu-id="eca2a-117">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eca2a-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
