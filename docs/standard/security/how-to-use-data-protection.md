---
title: '방법: 데이터 보호 사용'
description: .NET에서 DPAPI (데이터 보호 API)에 액세스 하 여 데이터 보호를 사용 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: c7f88105727dfd33c87a815054aa317ac2052e83
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598595"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="e005c-103">방법: 데이터 보호 사용</span><span class="sxs-lookup"><span data-stu-id="e005c-103">How to: Use Data Protection</span></span>
<span data-ttu-id="e005c-104">.NET Framework는 현재 사용자 계정 또는 컴퓨터의 정보를 사용하여 데이터를 암호화할 수 있게 해주는 DPAPI(데이터 보호 API)에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-104">The .NET Framework provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="e005c-105">DPAPI를 사용하는 경우 명시적으로 암호화 키를 생성 및 저장하는 어려운 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-105">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
 <span data-ttu-id="e005c-106"><xref:System.Security.Cryptography.ProtectedMemory> 클래스를 사용하여 메모리 내 바이트 배열을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-106">Use the <xref:System.Security.Cryptography.ProtectedMemory> class to encrypt an array of in-memory bytes.</span></span>  <span data-ttu-id="e005c-107">이 기능은 Microsoft Windows XP 이상의 운영 체제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-107">This functionality is available in Microsoft Windows XP and later operating systems.</span></span>  <span data-ttu-id="e005c-108">현재 프로세스에서 암호화된 메모리가 현재 프로세스에서만, 모든 프로세스에서 또는 동일한 사용자 컨텍스트에서 암호 해독할 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-108">You can specify that memory encrypted by the current process can be decrypted by the current process only, by all processes, or from the same user context.</span></span>  <span data-ttu-id="e005c-109"><xref:System.Security.Cryptography.ProtectedMemory> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.MemoryProtectionScope> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e005c-109">See the <xref:System.Security.Cryptography.MemoryProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedMemory> options.</span></span>  
  
 <span data-ttu-id="e005c-110"><xref:System.Security.Cryptography.ProtectedData> 클래스를 사용하여 바이트 배열 복사본을 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-110">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="e005c-111">이 기능은 Microsoft Windows 2000 이상의 운영 체제에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-111">This functionality is available in Microsoft Windows 2000 and later operating systems.</span></span>  <span data-ttu-id="e005c-112">현재 사용자 계정에서 암호화된 데이터가 동일한 사용자 계정에 의해서만 암호 해독될 수 있도록 지정하거나, 현재 사용자 계정에서 암호화된 데이터가 컴퓨터의 모든 계정에 의해 암호 해독될 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-112">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="e005c-113"><xref:System.Security.Cryptography.ProtectedData> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.DataProtectionScope> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e005c-113">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="e005c-114">데이터 보호를 사용하여 메모리 내 데이터를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="e005c-114">To encrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="e005c-115">암호화할 바이트 배열, 엔트로피 및 메모리 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-115">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the memory protection scope.</span></span>  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a><span data-ttu-id="e005c-116">데이터 보호를 사용하여 메모리 내 데이터를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="e005c-116">To decrypt in-memory data using data protection</span></span>  
  
1. <span data-ttu-id="e005c-117">암호 해독할 바이트 배열 및 메모리 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-117">Call the static <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> method while passing an array of bytes to decrypt and the memory protection scope.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="e005c-118">데이터 보호를 사용하여 파일 또는 스트림에 데이터를 암호화하려면</span><span class="sxs-lookup"><span data-stu-id="e005c-118">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="e005c-119">임의 엔트로피를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-119">Create random entropy.</span></span>  
  
2. <span data-ttu-id="e005c-120">암호화할 바이트 배열, 엔트로피 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Protect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-120">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="e005c-121">파일 또는 스트림에 암호화된 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-121">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="e005c-122">데이터 보호를 사용하여 파일 또는 스트림에서 데이터를 암호 해독하려면</span><span class="sxs-lookup"><span data-stu-id="e005c-122">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="e005c-123">파일 또는 스트림에서 암호화된 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-123">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="e005c-124">암호 해독할 바이트 배열 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-124">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e005c-125">예제</span><span class="sxs-lookup"><span data-stu-id="e005c-125">Example</span></span>  
 <span data-ttu-id="e005c-126">다음 코드 예제에서는 두 가지 형태의 암호화 및 암호 해독을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-126">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="e005c-127">먼저 코드 예제에서 메모리 내 바이트 배열을 암호화한 다음 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-127">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="e005c-128">그런 다음 코드 예제에서 바이트 배열의 복사본을 암호화하고 파일에 저장한 다음 파일에서 다시 데이터를 로드하고 데이터를 암호 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-128">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="e005c-129">이 예제에서는 원본 데이터, 암호화된 데이터 및 암호 해독된 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-129">The example displays the original data, the encrypted data, and the decrypted data.</span></span>  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e005c-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e005c-130">Compiling the Code</span></span>  
  
- <span data-ttu-id="e005c-131">`System.Security.dll`에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-131">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="e005c-132"><xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> 및 <xref:System.Text> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e005c-132">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e005c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e005c-133">See also</span></span>

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
