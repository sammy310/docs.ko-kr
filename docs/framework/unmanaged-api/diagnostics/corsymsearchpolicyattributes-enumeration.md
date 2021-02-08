---
description: '자세한 정보: CorSymSearchPolicyAttributes 열거형'
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
ms.openlocfilehash: a9af0e96809ec8eba5c03c2e372e818c74914baf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800476"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="06920-103">CorSymSearchPolicyAttributes 열거형</span><span class="sxs-lookup"><span data-stu-id="06920-103">CorSymSearchPolicyAttributes Enumeration</span></span>

<span data-ttu-id="06920-104">기호 판독기를 검색할 때 사용할 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06920-104">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="06920-105">이러한 상수는 [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) 및 [ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) 메서드에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06920-105">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="06920-106">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06920-106">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06920-107">구문</span><span class="sxs-lookup"><span data-stu-id="06920-107">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="06920-108">구성원</span><span class="sxs-lookup"><span data-stu-id="06920-108">Members</span></span>  
  
|<span data-ttu-id="06920-109">멤버</span><span class="sxs-lookup"><span data-stu-id="06920-109">Member</span></span>|<span data-ttu-id="06920-110">설명</span><span class="sxs-lookup"><span data-stu-id="06920-110">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="06920-111">레지스트리에 기호 검색 경로를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06920-111">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="06920-112">기호 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="06920-112">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="06920-113">디버그 디렉터리에 지정 된 경로를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="06920-113">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="06920-114">.Exe 파일이 인 위치에서 PDB를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="06920-114">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06920-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06920-115">Requirements</span></span>  

 <span data-ttu-id="06920-116">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="06920-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06920-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06920-117">See also</span></span>

- [<span data-ttu-id="06920-118">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="06920-118">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
