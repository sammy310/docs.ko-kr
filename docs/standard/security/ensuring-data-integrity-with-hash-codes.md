---
title: 해시 코드를 사용하여 데이터 무결성 보장
description: .NET의 해시 코드를 사용 하 여 데이터 무결성을 보장 하는 방법을 알아봅니다. 해시 값을 데이터를 고유하게 식별하는 고정 길이 숫자 값입니다.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 3205e37f283cb205f5edfc5948a9cb9f7256f752
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556958"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="e2345-104">해시 코드를 사용하여 데이터 무결성 보장</span><span class="sxs-lookup"><span data-stu-id="e2345-104">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="e2345-105">해시 값을 데이터를 고유하게 식별하는 고정 길이 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="e2345-106">해시 값은 대용량 데이터를 훨씬 더 작은 숫자 값으로 나타내므로 디지털 서명과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="e2345-107">해시 값에 서명하는 것이 더 큰 값에 서명하는 것보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="e2345-108">해시 값은 안전하지 않은 채널을 통해 전송된 데이터의 무결성을 확인하는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="e2345-109">수신된 데이터의 해시 값을 전송된 데이터의 해시 값과 비교하여 데이터가 변경되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="e2345-110">이 항목에서는 <xref:System.Security.Cryptography> 네임스페이스의 클래스를 사용하여 해시 코드를 생성하고 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="e2345-111">해시 생성</span><span class="sxs-lookup"><span data-stu-id="e2345-111">Generating a Hash</span></span>

 <span data-ttu-id="e2345-112">관리되는 해시 클래스는 바이트 배열이나 관리되는 스트림 개체를 해시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="e2345-113">다음 예제에서는 SHA1 해시 알고리즘을 사용하여 문자열에 대한 해시 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="e2345-114">이 예제에서는 <xref:System.Text.UnicodeEncoding> 클래스를 사용하여 문자열을 <xref:System.Security.Cryptography.SHA256> 클래스를 통해 해시된 바이트 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="e2345-115">해시 값이 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="e2345-116">이 코드는 다음 문자열을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="e2345-117">해시 확인</span><span class="sxs-lookup"><span data-stu-id="e2345-117">Verifying a Hash</span></span>

 <span data-ttu-id="e2345-118">데이터를 해시 값과 비교하여 데이터 무결성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="e2345-119">일반적으로 데이터는 특정 시간에 해시되고 해시 값은 몇 가지 방법으로 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="e2345-120">나중에 데이터를 다시 해시하고 보호된 값과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="e2345-121">해시 값이 일치하면 데이터가 변경되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="e2345-122">값이 일치하지 않으면 데이터가 손상된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="e2345-123">이 시스템이 작동하려면 보호된 해시를 암호화하거나 모든 신뢰할 수 없는 상대방으로부터 기밀로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="e2345-124">다음 예제에서는 문자열의 이전 해시 값을 새 해시 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="e2345-125">이 예제에서는 해시 값의 각 바이트를 순환하고 비교를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="e2345-126">두 해시 값이 일치하면 이 코드는 다음 내용을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="e2345-127">일치하지 않으면 코드는 다음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2345-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2345-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2345-128">See also</span></span>

- [<span data-ttu-id="e2345-129">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="e2345-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="e2345-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="e2345-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="e2345-131">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="e2345-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="e2345-132">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="e2345-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
