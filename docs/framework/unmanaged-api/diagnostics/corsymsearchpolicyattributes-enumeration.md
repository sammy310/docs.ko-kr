---
title: CorSymSearchPolicyAttributes 열거형
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178343"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="20b5a-102">CorSymSearchPolicyAttributes 열거형</span><span class="sxs-lookup"><span data-stu-id="20b5a-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="20b5a-103">기호 판독기를 검색할 때 사용할 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="20b5a-104">이러한 상수는 [ISymUnmanaged바인더2:GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) 및 [ISymUnmanaged바인더3:GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) 메서드에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="20b5a-105">신뢰할 수 없는 원본에서 프로그램 데이터베이스(PDB) 파일을 여는 것은 보안 위험입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b5a-106">구문</span><span class="sxs-lookup"><span data-stu-id="20b5a-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="20b5a-107">구성원</span><span class="sxs-lookup"><span data-stu-id="20b5a-107">Members</span></span>  
  
|<span data-ttu-id="20b5a-108">멤버</span><span class="sxs-lookup"><span data-stu-id="20b5a-108">Member</span></span>|<span data-ttu-id="20b5a-109">Description</span><span class="sxs-lookup"><span data-stu-id="20b5a-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="20b5a-110">기호 검색 경로에 대 한 레지스트리를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="20b5a-111">기호 서버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="20b5a-112">디버그 디렉토리에 지정된 경로를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="20b5a-113">.exe 파일이 있는 위치에 있는 PDB를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20b5a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20b5a-114">Requirements</span></span>  
 <span data-ttu-id="20b5a-115">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="20b5a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b5a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b5a-116">See also</span></span>

- [<span data-ttu-id="20b5a-117">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="20b5a-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
