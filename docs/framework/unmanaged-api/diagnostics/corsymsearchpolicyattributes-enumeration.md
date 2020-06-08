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
ms.openlocfilehash: 8af71314cf8a24c710d3b8980c082daaf9186715
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501874"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="f7f02-102">CorSymSearchPolicyAttributes 열거형</span><span class="sxs-lookup"><span data-stu-id="f7f02-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="f7f02-103">기호 판독기를 검색할 때 사용할 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="f7f02-104">이러한 상수는 [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) 및 [ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f7f02-105">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f02-106">구문</span><span class="sxs-lookup"><span data-stu-id="f7f02-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="f7f02-107">멤버</span><span class="sxs-lookup"><span data-stu-id="f7f02-107">Members</span></span>  
  
|<span data-ttu-id="f7f02-108">멤버</span><span class="sxs-lookup"><span data-stu-id="f7f02-108">Member</span></span>|<span data-ttu-id="f7f02-109">설명</span><span class="sxs-lookup"><span data-stu-id="f7f02-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="f7f02-110">레지스트리에 기호 검색 경로를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="f7f02-111">기호 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="f7f02-112">디버그 디렉터리에 지정 된 경로를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="f7f02-113">.Exe 파일이 인 위치에서 PDB를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f02-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7f02-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7f02-114">Requirements</span></span>  
 <span data-ttu-id="f7f02-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f7f02-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f02-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7f02-116">See also</span></span>

- [<span data-ttu-id="f7f02-117">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="f7f02-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
