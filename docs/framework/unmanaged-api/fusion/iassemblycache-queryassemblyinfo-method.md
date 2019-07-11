---
title: IAssemblyCache::QueryAssemblyInfo 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.QueryAssemblyInfo
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a336e2d4516eaa43decf156f25a62729859a3ff0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778715"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="41c35-102">IAssemblyCache::QueryAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="41c35-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="41c35-103">지정된 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41c35-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c35-104">구문</span><span class="sxs-lookup"><span data-stu-id="41c35-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41c35-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41c35-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="41c35-106">[in] 같은 값이 지원에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="41c35-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="41c35-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41c35-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="41c35-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="41c35-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="41c35-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="41c35-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="41c35-110">[in] 데이터를 검색 하는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41c35-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="41c35-111">[out에서] [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) 어셈블리에 대 한 데이터를 포함 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="41c35-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c35-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41c35-112">Requirements</span></span>  
 <span data-ttu-id="41c35-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41c35-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41c35-114">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="41c35-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="41c35-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41c35-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c35-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="41c35-116">See also</span></span>

- [<span data-ttu-id="41c35-117">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41c35-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
