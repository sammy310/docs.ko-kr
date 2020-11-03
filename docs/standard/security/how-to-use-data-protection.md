---
title: '방법: 데이터 보호 사용'
description: .NET에서 DPAPI (데이터 보호 API)에 액세스 하 여 데이터 보호를 사용 하는 방법에 대해 알아봅니다.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: d3fe7ef3ddbc6e75a248101829b11a8abcb3c15a
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282052"
---
# <a name="how-to-use-data-protection"></a>방법: 데이터 보호 사용

> [!NOTE]
> 이 문서는 Windows에 적용 됩니다.
>
> ASP.NET Core에 대 한 자세한 내용은 [데이터 보호 ASP.NET Core](/aspnet/core/security/data-protection/introduction)를 참조 하세요.

.NET에서는 DPAPI (데이터 보호 API)에 대 한 액세스를 제공 하므로 현재 사용자 계정 또는 컴퓨터의 정보를 사용 하 여 데이터를 암호화할 수 있습니다.  DPAPI를 사용하는 경우 명시적으로 암호화 키를 생성 및 저장하는 어려운 문제가 완화됩니다.  
  
<xref:System.Security.Cryptography.ProtectedData> 클래스를 사용하여 바이트 배열 복사본을 암호화합니다. 이 기능은 .NET Framework, .NET Core 및 .NET 5에서 사용할 수 있습니다.  현재 사용자 계정에서 암호화된 데이터가 동일한 사용자 계정에 의해서만 암호 해독될 수 있도록 지정하거나, 현재 사용자 계정에서 암호화된 데이터가 컴퓨터의 모든 계정에 의해 암호 해독될 수 있도록 지정할 수 있습니다.  <xref:System.Security.Cryptography.ProtectedData> 옵션에 대한 자세한 내용은 <xref:System.Security.Cryptography.DataProtectionScope> 열거형을 참조하세요.  
  
## <a name="encrypt-data-to-a-file-or-stream-using-data-protection"></a>데이터 보호를 사용 하 여 파일 또는 스트림으로 데이터 암호화  
  
1. 임의 엔트로피를 만듭니다.  
  
2. 암호화할 바이트 배열, 엔트로피 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Protect%2A> 메서드를 호출합니다.  
  
3. 파일 또는 스트림에 암호화된 데이터를 씁니다.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>데이터 보호를 사용하여 파일 또는 스트림에서 데이터를 암호 해독하려면  
  
1. 파일 또는 스트림에서 암호화된 데이터를 읽습니다.  
  
2. 암호 해독할 바이트 배열 및 데이터 보호 범위를 전달하는 동안 정적 <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> 메서드를 호출합니다.  
  
## <a name="example"></a>예제

다음 코드 예제에서는 두 가지 형태의 암호화 및 암호 해독을 보여 줍니다.  먼저 코드 예제에서 메모리 내 바이트 배열을 암호화한 다음 암호 해독합니다.  그런 다음 코드 예제에서 바이트 배열의 복사본을 암호화하고 파일에 저장한 다음 파일에서 다시 데이터를 로드하고 데이터를 암호 해독합니다.  이 예제에서는 원본 데이터, 암호화된 데이터 및 암호 해독된 데이터를 표시합니다.

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  

이 예제는 Windows에서 .NET Framework 및 실행을 대상으로 하는 경우에만 컴파일되고 실행 됩니다.

- `System.Security.dll`에 대한 참조를 포함합니다.  
  
- <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> 및 <xref:System.Text> 네임스페이스를 포함합니다.  
  
## <a name="see-also"></a>참고 항목

- [암호화 모델](cryptography-model.md)
- [암호화 서비스](cryptographic-services.md)
- [플랫폼 간 암호화](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [ASP.NET Core 데이터 보호](/aspnet/core/security/data-protection/introduction)
