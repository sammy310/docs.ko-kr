---
title: 암호화 및 Visual Basic의 문자열을 암호 해독
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 1d003df87327e14a6cbd65222f86c3dc4df169ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024484"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>연습: 암호화 및 Visual Basic의 문자열을 암호 해독
이 연습에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Security.Cryptography.DESCryptoServiceProvider> 암호화 및 3des(triple Data Encryption Standard의 암호화 서비스 공급자 (CSP) 버전을 사용 하 여 문자열을 해독 하는 클래스 (<xref:System.Security.Cryptography.TripleDES>) 알고리즘입니다. 첫 번째 단계는 3DES 알고리즘을 캡슐화 하 고 base-64로 인코딩된 문자열로 암호화 된 데이터를 저장 하는 간단한 래퍼 클래스를 만드는 것입니다. 그런 다음 해당 래퍼를 사용 하 여 안전 하 게 공개적으로 액세스할 텍스트 파일에서 사용자 개인 데이터를 저장 합니다.  
  
 사용자 비밀 (예: 암호)를 보호 하 고 자격 증명을 권한이 없는 사용자가 읽을 수 있도록 암호화를 사용할 수 있습니다. 이 사용자의 자산을 보호 하 고 부인 방지를 제공 하는 도난 으로부터 권한 있는 사용자의 id를 보호할 수 있습니다. 암호화는 무단으로 액세스 하지 못하게 사용자의 데이터를 보호할 수도 있습니다.  
  
 자세한 내용은 [암호화 서비스](../../../../standard/security/cryptographic-services.md)를 참조하세요.  
  
> [!IMPORTANT]
>  Rijndael (이제 이라고 Advanced Encryption Standard [AES]) 및 3des(triple Data Encryption Standard () 알고리즘에 더 때문에 DES 보다 강력한 보안을 제공할 계산 집약적. 자세한 내용은 <xref:System.Security.Cryptography.DES> 및 <xref:System.Security.Cryptography.Rijndael>를 참조하세요.  
  
### <a name="to-create-the-encryption-wrapper"></a>암호화 래퍼를 만들려면  
  
1. 만들기는 `Simple3Des` 암호화 및 암호 해독 메서드를 캡슐화 하는 클래스입니다.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. 암호화 네임 스페이스 가져오기를 포함 하는 파일의 시작 부분에 추가 된 `Simple3Des` 클래스입니다.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. 에 `Simple3Des` 클래스 3DES 암호화 서비스 공급자를 저장 하는 개인 필드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. 지정 된 길이의 바이트 배열에 지정 된 키의 해시에서 만드는 개인 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. 3DES 암호화 서비스 공급자를 초기화 하는 생성자를 추가 합니다.  
  
     합니다 `key` 매개 변수를 `EncryptData` 고 `DecryptData` 메서드.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. 문자열을 암호화 하는 공용 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. 문자열을 해독 하는 공용 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     래퍼 클래스 사용자 자산을 보호 하기 위해 이제 사용할 수 있습니다. 이 예제에서는 공개적으로 액세스할 텍스트 파일에서 사용자 개인 데이터를 안전 하 게 저장에 사용 됩니다.  
  
### <a name="to-test-the-encryption-wrapper"></a>암호화 래퍼를 테스트 하려면  
  
1. 별도 클래스는 래퍼를 사용 하는 메서드 추가 `EncryptData` 문자열을 암호화 하 고 사용자에 게 작성 방법의 내 문서 폴더입니다.  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. 내 문서 폴더 사용자에서 암호화 된 문자열을 읽는 메서드를 추가 하는 래퍼를 사용 하 여 문자열을 해독 `DecryptData` 메서드.  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. 호출 하는 사용자 인터페이스 코드를 추가 합니다 `TestEncoding` 및 `TestDecoding` 메서드.  
  
4. 애플리케이션을 실행합니다.  
  
     응용 프로그램을 테스트 하는 해독 되지 않습니다 데이터가 잘못 된 암호를 제공 하는 경우 알 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
