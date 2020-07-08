---
title: MailAddressParser 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051352"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="aabf2-102">MailAddressParser 클래스</span><span class="sxs-lookup"><span data-stu-id="aabf2-102">MailAddressParser class</span></span>

<span data-ttu-id="aabf2-103">RFC 2822에 설명 된 대로 전자 메일 주소를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="aabf2-104">이 클래스는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="aabf2-105">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="aabf2-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="aabf2-107">ParseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="aabf2-107">ParseAddress method</span></span>

<span data-ttu-id="aabf2-108">지정 된 문자열에서 단일 전자 메일 주소를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="aabf2-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aabf2-109">Parameters</span></span>

<span data-ttu-id="aabf2-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="aabf2-110">`data` <xref:System.String></span></span>

<span data-ttu-id="aabf2-111">구문 분석할 전자 메일 주소를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="aabf2-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="aabf2-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="aabf2-113">유효한 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="aabf2-114">예외</span><span class="sxs-lookup"><span data-stu-id="aabf2-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="aabf2-115">전자 메일 주소가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aabf2-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="aabf2-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aabf2-116">Requirements</span></span>

<span data-ttu-id="aabf2-117">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="aabf2-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="aabf2-118">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="aabf2-118">**Assembly:** System (in System.dll)</span></span>
