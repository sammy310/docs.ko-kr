---
title: 데이터 암호 해독
description: 대칭 알고리즘 또는 비대칭 알고리즘을 사용 하 여 .NET에서 데이터의 암호를 해독 하는 방법에 대해 알아봅니다.
ms.date: 03/22/2021
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 14d8b6185c1c5b3aaee4f2041f98c500f2d3c313
ms.sourcegitcommit: 26721a2260deabb3318cc98af8619306711153cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "105027911"
---
# <a name="decrypting-data"></a>데이터 암호 해독

암호 해독은 암호화의 반대 작업입니다. 비밀 키 암호화의 경우 데이터를 암호화하는 데 사용된 키 및 IV를 모두 알고 있어야 합니다. 퍼블릭 키 암호화의 경우 퍼블릭 키(프라이빗 키를 사용하여 데이터가 암호화된 경우) 또는 프라이빗 키(퍼블릭 키를 사용하여 데이터가 암호화된 경우)를 알고 있어야 합니다.

## <a name="symmetric-decryption"></a>대칭 암호 해독

대칭 알고리즘을 사용하여 암호화된 데이터의 암호 해독은 대칭 알고리즘을 사용하여 데이터를 암호화하는 데 사용된 프로세스와 비슷합니다. 클래스는 관리 되는 <xref:System.Security.Cryptography.CryptoStream> 스트림 개체에서 읽은 데이터를 해독 하기 위해 .net에서 제공 하는 대칭 암호화 클래스와 함께 사용 됩니다.

다음 예제에서는 알고리즘에 대 한 기본 구현 클래스의 새 인스턴스를 만드는 방법을 보여 줍니다 <xref:System.Security.Cryptography.Aes> . 인스턴스는 개체에 대 한 암호 해독을 수행 하는 데 사용 됩니다 <xref:System.Security.Cryptography.CryptoStream> . 이 예제에서는 먼저 구현 클래스의 새 인스턴스를 만듭니다 <xref:System.Security.Cryptography.Aes> . 관리 되는 스트림 변수에서 IV (초기화 벡터) 값을 읽습니다 `myStream` . 그런 다음 개체를 인스턴스화하고 <xref:System.Security.Cryptography.CryptoStream> 인스턴스의 값으로 초기화 `myStream` 합니다. <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType>인스턴스의 메서드에는 <xref:System.Security.Cryptography.Aes> IV 값과 암호화에 사용 된 동일한 키가 전달 됩니다.

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(
    myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(
    myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

다음 예제에서는 스트림을 만들고, 스트림을 암호 해독하고, 스트림에서 읽고, 스트림을 닫는 전체 프로세스를 보여 줍니다. *TestData.txt* 라는 파일을 읽는 파일 스트림 개체가 만들어집니다. 그런 다음 **CryptoStream** 클래스와 **Aes** 클래스를 사용 하 여 파일 스트림을 해독 합니다. 이 예에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에서 사용 되는 키 값을 지정 합니다. 이러한 값을 암호화 및 전송하는 데 필요한 코드는 표시되지 않습니다.

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

앞의 예제에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에 사용 된 것과 동일한 키와 알고리즘을 사용 합니다. 해당 예제에서 만든 *TestData.txt* 파일의 암호를 해독 하 고 콘솔에 원래 텍스트를 표시 합니다.

## <a name="asymmetric-decryption"></a>비대칭 암호 해독

일반적으로 당사자(당사자 A)는 퍼블릭 키와 프라이빗 키를 둘 다 생성하고 메모리 또는 암호화 키 컨테이너에 키를 저장합니다. 당사자 A가 다른 당사자(당사자 B)에게 공개 키를 보냅니다. 공개 키를 사용 하 여 파티 B는 데이터를 암호화 하 고 파티 A에 데이터를 다시 보냅니다. 파티는 데이터를 받은 후에 해당 하는 개인 키를 사용 하 여 암호를 해독 합니다. 암호 해독은 당사자 A가 당사자 B에서 데이터를 암호화하는 데 사용한 퍼블릭 키에 해당하는 프라이빗 키를 사용하는 경우에만 성공합니다.

안전한 암호화 키 컨테이너에 비대칭 키를 저장하는 방법 및 나중에 비대칭 키를 검색하는 방법에 대한 자세한 내용은 [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md)을 참조하세요.

다음 예제에서는 대칭 키 및 IV를 나타내는 두 바이트 배열의 암호 해독을 보여 줍니다. 제3자에게 쉽게 보낼 수 있는 형식으로 <xref:System.Security.Cryptography.RSA> 개체에서 비대칭 공개 키를 추출하는 방법에 대한 자세한 내용은 [Encrypting Data](encrypting-data.md)이라는 관리되는 스트림의 값으로 초기화합니다.

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a>참고 항목

- [암호화 및 암호 해독을 위한 키 생성](generating-keys-for-encryption-and-decryption.md)
- [데이터 암호화](encrypting-data.md)
- [암호화 서비스](cryptographic-services.md)
- [암호화 모델](cryptography-model.md)
- [플랫폼 간 암호화](cross-platform-cryptography.md)
- [패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성](vulnerabilities-cbc-mode.md)
- [ASP.NET Core 데이터 보호](/aspnet/core/security/data-protection/introduction)
