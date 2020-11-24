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
ms.openlocfilehash: f764be9b80a8d4dcb15791d406412ece9e7e7c87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670929"
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="cad92-102">IAssemblyCache::QueryAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="cad92-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>

<span data-ttu-id="cad92-103">지정 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cad92-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad92-104">구문</span><span class="sxs-lookup"><span data-stu-id="cad92-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cad92-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cad92-105">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="cad92-106">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cad92-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="cad92-107">지원되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cad92-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="cad92-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="cad92-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
- <span data-ttu-id="cad92-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="cad92-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="cad92-110">진행 데이터가 검색 될 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cad92-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="cad92-111">[in, out] 어셈블리에 대 한 데이터를 포함 하는 [ASSEMBLY_INFO](assembly-info-structure.md) 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="cad92-111">[in, out] An [ASSEMBLY_INFO](assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cad92-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cad92-112">Requirements</span></span>  

 <span data-ttu-id="cad92-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cad92-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cad92-114">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cad92-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cad92-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cad92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad92-116">참조</span><span class="sxs-lookup"><span data-stu-id="cad92-116">See also</span></span>

- [<span data-ttu-id="cad92-117">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cad92-117">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
