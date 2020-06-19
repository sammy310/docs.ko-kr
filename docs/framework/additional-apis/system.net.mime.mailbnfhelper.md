---
title: MailBnfHelper 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990468"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="378f9-102">MailBnfHelper 클래스</span><span class="sxs-lookup"><span data-stu-id="378f9-102">MailBnfHelper class</span></span>

<span data-ttu-id="378f9-103">인터넷 메시지 형식 문자열을 구문 분석 하는 유틸리티 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="378f9-104">이 클래스는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="378f9-105">이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="378f9-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="378f9-107">Ascii7bitMaxValue 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="378f9-108">최대 7 비트 Ascii 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="378f9-109">텍스트 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-109">Atext field</span></span>

<span data-ttu-id="378f9-110">Atom에 허용 되는 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="378f9-111">CR 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-111">CR field</span></span>

<span data-ttu-id="378f9-112">캐리지 리턴 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="378f9-113">Ctext 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-113">Ctext field</span></span>

<span data-ttu-id="378f9-114">주석 내에서 허용 되는 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="378f9-115">점 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-115">Dot field</span></span>

<span data-ttu-id="378f9-116">전체 중지 문자 ()를 나타냅니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="378f9-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="378f9-117">EndComment 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-117">EndComment field</span></span>

<span data-ttu-id="378f9-118">주석의 끝을 지정 하는 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="378f9-119">LF 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-119">LF field</span></span>

<span data-ttu-id="378f9-120">줄 바꿈 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="378f9-121">공간 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-121">Space field</span></span>

<span data-ttu-id="378f9-122">공백 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="378f9-123">StartComment 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-123">StartComment field</span></span>

<span data-ttu-id="378f9-124">주석의 시작을 지정 하는 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="378f9-125">탭 필드</span><span class="sxs-lookup"><span data-stu-id="378f9-125">Tab field</span></span>

<span data-ttu-id="378f9-126">탭 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="378f9-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="378f9-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="378f9-127">Requirements</span></span>

<span data-ttu-id="378f9-128">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="378f9-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="378f9-129">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="378f9-129">**Assembly:** System (in System.dll)</span></span>
