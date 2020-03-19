---
title: CBC 암호 해독 취약점
description: 패딩을 사용하여 CBC(암호-블록 체인) 모드 대칭 암호 해독을 사용하여 타이밍 취약점을 감지하고 완화하는 방법을 알아봅니다.
ms.date: 06/12/2018
author: blowdart
ms.openlocfilehash: 47520ea4c9c7d0ef4d79378c93c6ce1f2ba7dd6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186090"
---
# <a name="timing-vulnerabilities-with-cbc-mode-symmetric-decryption-using-padding"></a><span data-ttu-id="ffbd5-103">패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성</span><span class="sxs-lookup"><span data-stu-id="ffbd5-103">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>

<span data-ttu-id="ffbd5-104">Microsoft는 매우 구체적인 경우를 제외하고 는 검증 가능한 패딩이 적용되었을 때 CBC(암호 블록 체인) 대칭 암호화 모드로 암호화된 데이터를 해독하는 것이 더 이상 안전하지 않다고 생각합니다. 상황.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-104">Microsoft believes that it's no longer safe to decrypt data encrypted with the Cipher-Block-Chaining (CBC) mode of symmetric encryption when verifiable padding has been applied without first ensuring the integrity of the ciphertext, except for very specific circumstances.</span></span> <span data-ttu-id="ffbd5-105">이 판단은 현재 알려진 암호화 연구를 기반으로합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-105">This judgement is based on currently known cryptographic research.</span></span>

## <a name="introduction"></a><span data-ttu-id="ffbd5-106">소개</span><span class="sxs-lookup"><span data-stu-id="ffbd5-106">Introduction</span></span>

<span data-ttu-id="ffbd5-107">패딩 오라클 공격은 공격자가 키를 모르고 데이터 내용을 해독할 수 있도록 암호화된 데이터에 대한 공격 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-107">A padding oracle attack is a type of attack against encrypted data that allows the attacker to decrypt the contents of the data, without knowing the key.</span></span>

<span data-ttu-id="ffbd5-108">오라클은 공격자가 실행중인 작업이 올바른지 여부에 대한 정보를 제공하는 "tell"을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-108">An oracle refers to a "tell" which gives an attacker information about whether the action they're executing is correct or not.</span></span> <span data-ttu-id="ffbd5-109">어린이와 보드 또는 카드 게임을 상상해보십시오.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-109">Imagine playing a board or card game with a child.</span></span> <span data-ttu-id="ffbd5-110">그들은 좋은 움직임을 만들려고 생각하기 때문에 그들의 얼굴이 큰 미소로 점등 할 때, 그것은 오라클입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-110">When their face lights up with a big smile because they think they're about to make a good move, that's an oracle.</span></span> <span data-ttu-id="ffbd5-111">당신은, 상대로, 적절하게 다음 움직임을 계획하기 위해이 오라클을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-111">You, as the opponent, can use this oracle to plan your next move appropriately.</span></span>

<span data-ttu-id="ffbd5-112">패딩은 특정 암호화 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-112">Padding is a specific cryptographic term.</span></span> <span data-ttu-id="ffbd5-113">데이터를 암호화하는 데 사용되는 알고리즘인 일부 암호는 각 블록이 고정된 크기인 데이터 블록에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-113">Some ciphers, which are the algorithms used to encrypt your data, work on blocks of data where each block is a fixed size.</span></span> <span data-ttu-id="ffbd5-114">암호화하려는 데이터가 블록을 채우기에 적합한 크기가 아닌 경우 데이터가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-114">If the data you want to encrypt isn't the right size to fill the blocks, your data is padded until it does.</span></span> <span data-ttu-id="ffbd5-115">많은 형태의 패딩은 원래 입력이 올바른 크기인 경우에도 패딩이 항상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-115">Many forms of padding require that padding to always be present, even if the original input was of the right size.</span></span> <span data-ttu-id="ffbd5-116">이렇게 하면 암호 해독 시 항상 패딩을 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-116">This allows the padding to always be safely removed upon decryption.</span></span>

<span data-ttu-id="ffbd5-117">두 가지를 결합하면 패딩 오라클이 있는 소프트웨어 구현을 통해 해독된 데이터가 유효한 패딩이 있는지 여부를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-117">Putting the two things together, a software implementation with a padding oracle reveals whether decrypted data has valid padding.</span></span> <span data-ttu-id="ffbd5-118">오라클은 "잘못된 패딩"이라는 값을 반환하는 것과 같이 간단하거나 유효하지 않은 블록이 아닌 유효한 블록을 처리하는 데 매우 다른 시간을 보내는 것과 같이 더 복잡한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-118">The oracle could be something as simple as returning a value that says "Invalid padding" or something more complicated like taking a measurably different time to process a valid block as opposed to an invalid block.</span></span>

<span data-ttu-id="ffbd5-119">블록 기반 암호에는 첫 번째 블록의 데이터와 두 번째 블록의 데이터 관계를 결정하는 모드라는 다른 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-119">Block-based ciphers have another property, called the mode, which determines the relationship of data in the first block to the data in the second block, and so on.</span></span> <span data-ttu-id="ffbd5-120">가장 일반적으로 사용되는 모드 중 하나는 CBC입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-120">One of the most commonly used modes is CBC.</span></span> <span data-ttu-id="ffbd5-121">CBC는 초기화 벡터(IV)라고 하는 초기 임의 블록을 도입하고 이전 블록을 정적 암호화의 결과와 결합하여 동일한 키로 동일한 메시지를 암호화해도 항상 동일한 암호화된 출력이 생성되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-121">CBC introduces an initial random block, known as the Initialization Vector (IV), and combines the previous block with the result of static encryption to make it such that encrypting the same message with the same key doesn't always produce the same encrypted output.</span></span>

<span data-ttu-id="ffbd5-122">공격자는 CBC 데이터의 구조와 함께 패딩 오라클을 사용하여 오라클을 노출하는 코드로 약간 변경된 메시지를 보내고 오라클이 데이터가 정확하다고 말할 때까지 데이터를 계속 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-122">An attacker can use a padding oracle, in combination with how CBC data is structured, to send slightly changed messages to the code that exposes the oracle, and keep sending data until the oracle tells them the data is correct.</span></span> <span data-ttu-id="ffbd5-123">이 응답에서 공격자는 메시지 바이트바이트를 바이트별로 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-123">From this response, the attacker can decrypt the message byte by byte.</span></span>

<span data-ttu-id="ffbd5-124">최신 컴퓨터 네트워크는 공격자가 원격 시스템의 실행 시간에서 매우 작은(0.1ms 미만) 차이를 감지할 수 있는 고품질입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-124">Modern computer networks are of such high quality that an attacker can detect very small (less than 0.1 ms) differences in execution time on remote systems.</span></span><span data-ttu-id="ffbd5-125">데이터가 변조되지 않은 경우에만 성공적인 암호 해독이 발생할 수 있다고 가정하는 응용 프로그램은 성공 및 실패 한 암호 해독의 차이를 관찰하도록 설계된 도구의 공격에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-125"> Applications that are assuming that a successful decryption can only happen when the data wasn't tampered with may be vulnerable to attack from tools that are designed to observe differences in successful and unsuccessful decryption.</span></span> <span data-ttu-id="ffbd5-126">이러한 타이밍 차이는 일부 언어 나 라이브러리에서 다른 언어 나 라이브러리에서 더 중요 할 수 있지만, 이제 는 실패에 대한 응용 프로그램의 응답을 고려할 때 모든 언어와 라이브러리에 대한 실질적인 위협이라고 생각됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-126">While this timing difference may be more significant in some languages or libraries than others, it's now believed that this is a practical threat for all languages and libraries when the application's response to failure is taken into account.</span></span>

<span data-ttu-id="ffbd5-127">이 공격은 암호화된 데이터를 변경하고 오라클을 사용하여 결과를 테스트하는 기능에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-127">This attack relies on the ability to change the encrypted data and test the result with the oracle.</span></span> <span data-ttu-id="ffbd5-128">공격을 완전히 완화하는 유일한 방법은 암호화된 데이터의 변경 내용을 감지하고 해당 데이터에 대한 작업을 수행하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-128">The only way to fully mitigate the attack is to detect changes to the encrypted data and refuse to perform any actions on it.</span></span> <span data-ttu-id="ffbd5-129">이 작업을 수행하는 표준 방법은 데이터에 대한 서명을 만들고 작업을 수행하기 전에 해당 서명의 유효성을 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-129">The standard way to do this is to create a signature for the data and validate that signature before any operations are performed.</span></span> <span data-ttu-id="ffbd5-130">서명을 확인할 수 있어야 하고, 공격자가 만들 수 없으며, 그렇지 않으면 암호화된 데이터를 변경한 다음 변경된 데이터를 기반으로 새 서명을 계산해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-130">The signature must be verifiable, it cannot be created by the attacker, otherwise they'd change the encrypted data, then compute a new signature based on the changed data.</span></span> <span data-ttu-id="ffbd5-131">적절한 서명의 일반적인 유형 중 하나는 키 해시 메시지 인증 코드(HMAC)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-131">One common type of appropriate signature is known as a keyed-hash message authentication code (HMAC).</span></span> <span data-ttu-id="ffbd5-132">HMAC는 HMAC를 생산하는 사람과 이를 검증하는 사람에게만 알려진 비밀 키를 취한다는 점에서 체크섬과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-132">An HMAC differs from a checksum in that it takes a secret key, known only to the person producing the HMAC and to the person validating it.</span></span> <span data-ttu-id="ffbd5-133">키를 소유하지 않으면 올바른 HMAC를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-133">Without possession of the key, you can't produce a correct HMAC.</span></span> <span data-ttu-id="ffbd5-134">데이터를 받으면 암호화된 데이터를 가져가서 사용자와 보낸 사람 공유를 사용하여 HMAC를 독립적으로 계산한 다음 전송한 HMAC를 계산한 데이터와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-134">When you receive your data, you'd take the encrypted data, independently compute the HMAC using the secret key you and the sender share, then compare the HMAC they sent against the one you computed.</span></span> <span data-ttu-id="ffbd5-135">이 비교는 일정한 시간이어야 하며, 그렇지 않으면 다른 유형의 공격을 허용하는 다른 탐지 가능한 오라클을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-135">This comparison must be constant time, otherwise you've added another detectable oracle, allowing a different type of attack.</span></span>

<span data-ttu-id="ffbd5-136">요약하면 패딩된 CBC 블록 암호를 안전하게 사용하려면 데이터를 해독하기 전에 일정한 시간 비교를 사용하여 유효성을 검사하는 HMAC(또는 다른 데이터 무결성 검사)와 결합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-136">In summary, to use padded CBC block ciphers safely, you must combine them with an HMAC (or another data integrity check) that you validate using a constant time comparison before trying to decrypt the data.</span></span> <span data-ttu-id="ffbd5-137">변경된 모든 메시지는 응답을 생성하는 데 동일한 시간이 걸리므로 공격이 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-137">Since all altered messages take the same amount time to produce a response, the attack is prevented.</span></span>

## <a name="who-is-vulnerable"></a><span data-ttu-id="ffbd5-138">취약한 사람</span><span class="sxs-lookup"><span data-stu-id="ffbd5-138">Who is vulnerable</span></span>

<span data-ttu-id="ffbd5-139">이 취약점은 자체 암호화 및 암호 해독을 수행하는 관리되는 응용 프로그램과 네이티브 응용 프로그램 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-139">This vulnerability applies to both managed and native applications that are performing their own encryption and decryption.</span></span> <span data-ttu-id="ffbd5-140">여기에는 다음과 같은 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-140">This includes, for example:</span></span>

- <span data-ttu-id="ffbd5-141">나중에 서버의 암호 해독을 위해 쿠키를 암호화하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-141">An application that encrypts a cookie for later decryption on the server.</span></span>
- <span data-ttu-id="ffbd5-142">사용자가 나중에 열이 해독되는 테이블에 데이터를 삽입할 수 있는 기능을 제공하는 데이터베이스 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-142">A database application that provides the ability for users to insert data into a table whose columns are later decrypted.</span></span>
- <span data-ttu-id="ffbd5-143">전송 중 데이터를 보호하기 위해 공유 키를 사용하여 암호화에 의존하는 데이터 전송 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-143">A data transfer application that relies on encryption using a shared key to protect the data in transit.</span></span>
- <span data-ttu-id="ffbd5-144">TLS 터널을 "내부" 메시지 암호화 및 해독하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-144">An application that encrypts and decrypts messages "inside" the TLS tunnel.</span></span>

<span data-ttu-id="ffbd5-145">TLS만 사용하면 이러한 시나리오에서 사용자를 보호하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-145">Note that using TLS alone may not protect you in these scenarios.</span></span>

<span data-ttu-id="ffbd5-146">취약한 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="ffbd5-146">A vulnerable application:</span></span>

- <span data-ttu-id="ffbd5-147">PKCS#7 또는 ANSI X.923과 같은 검증 가능한 패딩 모드를 사용하여 CBC 암호 모드를 사용하여 데이터를 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-147">Decrypts data using the CBC cipher mode with a verifiable padding mode, such as PKCS#7 or ANSI X.923.</span></span>
- <span data-ttu-id="ffbd5-148">MAC 또는 비대칭 디지털 서명을 통해 데이터 무결성 검사를 수행하지 않고도 암호 해독을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-148">Performs the decryption without having performed a data integrity check (via a MAC or an asymmetric digital signature).</span></span>

<span data-ttu-id="ffbd5-149">이는 암호화 메시지 구문(PKCS#7/CMS) EnvelopedData 구조와 같은 이러한 기본 요소 위에 추상화 위에 구축된 응용 프로그램에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-149">This also applies to applications built on top of abstractions over top of these primitives, such as the Cryptographic Message Syntax (PKCS#7/CMS) EnvelopedData structure.</span></span>

## <a name="related-areas-of-concern"></a><span data-ttu-id="ffbd5-150">관련 관심 분야</span><span class="sxs-lookup"><span data-stu-id="ffbd5-150">Related areas of concern</span></span>

<span data-ttu-id="ffbd5-151">연구에 따르면 Microsoft는 메시지에 잘 알려져 있거나 예측 가능한 바닥글 구조가 있을 때 ISO 10126-동등한 패딩으로 패딩된 CBC 메시지에 대해 더 우려하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-151">Research has led Microsoft to be further concerned about CBC messages that are padded with ISO 10126-equivalent padding when the message has a well-known or predictable footer structure.</span></span> <span data-ttu-id="ffbd5-152">예를 들어 W3C XML 암호화 구문 및 처리 권장 사항(xmlenc, EncryptedXml)의 규칙에 따라 준비된 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-152">For example, content prepared under the rules of the W3C XML Encryption Syntax and Processing Recommendation (xmlenc, EncryptedXml).</span></span> <span data-ttu-id="ffbd5-153">메시지에 서명하는 W3C 지침에서 암호화가 적절한 것으로 간주되었지만 이제는 항상 암호화 후 기호를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-153">While the W3C guidance to sign the message then encrypt was considered appropriate at the time, Microsoft now recommends always doing encrypt-then-sign.</span></span>

<span data-ttu-id="ffbd5-154">응용 프로그램 개발자는 비대칭 키와 임의의 메시지 사이에 고유한 트러스트 관계가 없기 때문에 항상 비대칭 서명 키의 적용 가능성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-154">Application developers should always be mindful of verifying the applicability of an asymmetric signature key, as there's no inherent trust relationship between an asymmetric key and an arbitrary message.</span></span>

## <a name="details"></a><span data-ttu-id="ffbd5-155">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ffbd5-155">Details</span></span>

<span data-ttu-id="ffbd5-156">역사적으로 HMAC 또는 RSA 서명과 같은 수단을 사용하여 중요한 데이터를 암호화하고 인증하는 것이 중요하다는 합의가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-156">Historically, there has been consensus that it's important to both encrypt and authenticate important data, using means such as HMAC or RSA signatures.</span></span> <span data-ttu-id="ffbd5-157">그러나 암호화 및 인증 작업을 순서를 정하는 방법에 대한 명확한 지침이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-157">However, there has been less clear guidance as to how to sequence the encryption and authentication operations.</span></span> <span data-ttu-id="ffbd5-158">이 문서에 자세히 설명된 취약점으로 인해 Microsoft의 지침은 항상 "암호화-다음-기호" 패러다임을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-158">Due to the vulnerability detailed in this article, Microsoft's guidance is now to always use the "encrypt-then-sign" paradigm.</span></span> <span data-ttu-id="ffbd5-159">즉, 먼저 대칭 키를 사용하여 데이터를 암호화한 다음 암호문(암호화된 데이터)을 통해 MAC 또는 비대칭 서명을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-159">That is, first encrypt data using a symmetric key, then compute a MAC or asymmetric signature over the ciphertext (encrypted data).</span></span> <span data-ttu-id="ffbd5-160">데이터를 해독할 때는 그 반대의 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-160">When decrypting data, perform the reverse.</span></span> <span data-ttu-id="ffbd5-161">먼저 MAC 또는 암호 텍스트의 서명을 확인한 다음 암호를 해독합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-161">First, confirm the MAC or signature of the ciphertext, then decrypt it.</span></span>

<span data-ttu-id="ffbd5-162">"패딩 오라클 공격"으로 알려진 취약점의 클래스는 10 년 이상 존재하는 것으로 알려져있다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-162">A class of vulnerabilities known as "padding oracle attacks" have been known to exist for over 10 years.</span></span> <span data-ttu-id="ffbd5-163">이러한 취약점을 통해 공격자는 데이터 블록당 4096번의 시도를 하지 않고 AES 및 3DES와 같은 대칭 블록 알고리즘으로 암호화된 데이터를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-163">These vulnerabilities allow an attacker to decrypt data encrypted by symmetric block algorithms, such as AES and 3DES, using no more than 4096 attempts per block of data.</span></span> <span data-ttu-id="ffbd5-164">이러한 취약점은 블록 암호가 마지막에 검증 가능한 패딩 데이터와 함께 가장 자주 사용된다는 사실을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-164">These vulnerabilities make use of the fact that block ciphers are most frequently used with verifiable padding data at the end.</span></span> <span data-ttu-id="ffbd5-165">공격자가 암호텍스트를 변조하고 변조로 인해 마지막에 패딩 형식에 오류가 발생했는지 여부를 확인하면 공격자가 데이터를 해독할 수 있는 것으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-165">It was found that if an attacker can tamper with ciphertext and find out whether the tampering caused an error in the format of the padding at the end, the attacker can decrypt the data.</span></span>

<span data-ttu-id="ffbd5-166">처음에 실제 공격은 ASP.NET 취약점 [MS10-070과](/security-updates/SecurityBulletins/2010/ms10-070)같이 패딩이 유효한지 여부에 따라 다른 오류 코드를 반환하는 서비스를 기반으로 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-166">Initially, practical attacks were based on services that would return different error codes based on whether padding was valid, such as the ASP.NET vulnerability [MS10-070](/security-updates/SecurityBulletins/2010/ms10-070).</span></span> <span data-ttu-id="ffbd5-167">그러나 Microsoft는 이제 유효한 패딩 처리와 잘못된 패딩 처리 간의 타이밍 차이만 사용하여 유사한 공격을 수행하는 것이 실용적이라고 믿습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-167">However, Microsoft now believes that it's practical to conduct similar attacks using only the differences in timing between processing valid and invalid padding.</span></span>

<span data-ttu-id="ffbd5-168">암호화 체계가 서명을 사용하며 특정 데이터 길이에 대해 고정 된 런타임으로 서명 확인을 수행하면 [사이드 채널을](https://en.wikipedia.org/wiki/Side-channel_attack)통해 공격자에게 정보를 방출하지 않고도 데이터 무결성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-168">Provided that the encryption scheme employs a signature and that the signature verification is performed with a fixed runtime for a given length of data (irrespective of the contents), the data integrity can be verified without emitting any information to an attacker via a [side channel](https://en.wikipedia.org/wiki/Side-channel_attack).</span></span> <span data-ttu-id="ffbd5-169">무결성 검사는 변조된 메시지를 거부하므로 패딩 oracle 위협이 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-169">Since the integrity check rejects any tampered messages, the padding oracle threat is mitigated.</span></span>

## <a name="guidance"></a><span data-ttu-id="ffbd5-170">지침</span><span class="sxs-lookup"><span data-stu-id="ffbd5-170">Guidance</span></span>

<span data-ttu-id="ffbd5-171">무엇보다도 기밀성이 있는 데이터는 SSL(보안 소켓 계층)의 후속인 TLS(전송 계층 보안)를 통해 전송하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-171">First and foremost, Microsoft recommends that any data that has confidentiality needs be transmitted over Transport Layer Security (TLS), the successor to Secure Sockets Layer (SSL).</span></span>

<span data-ttu-id="ffbd5-172">다음으로 응용 프로그램을 분석하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-172">Next, analyze your application to:</span></span>

- <span data-ttu-id="ffbd5-173">수행 중인 암호화와 사용 중인 플랫폼 및 API에서 제공하는 암호화를 정확하게 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-173">Understand precisely what encryption you're performing and what encryption is being provided by the platforms and APIs you're using.</span></span>
- <span data-ttu-id="ffbd5-174">CBC 모드에서 AES 및 3DES와 같은 대칭 [블록 암호 알고리즘의](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers)각 계층에서 각각의 사용량에는 비밀 키 데이터 무결성 검사(비대칭 서명, HMAC) 또는 암호 모드를 GCM 또는 CCM과 같은 [인증된](https://en.wikipedia.org/wiki/Authenticated_encryption) 암호화(AE) 모드로 변경)의 사용이 통합되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-174">Be certain that each usage at each layer of a symmetric [block cipher algorithm](https://en.wikipedia.org/wiki/Block_cipher#Notable_block_ciphers), such as AES and 3DES, in CBC mode incorporate the use of a secret-keyed data integrity check (an asymmetric signature, an HMAC, or to change the cipher mode to an [authenticated encryption](https://en.wikipedia.org/wiki/Authenticated_encryption) (AE) mode such as GCM or CCM).</span></span>

<span data-ttu-id="ffbd5-175">현재 연구에 따르면 일반적으로 AE가 아닌 암호화 모드에 대해 인증 및 암호화 단계가 독립적으로 수행될 때 암호텍스트(암호화-다음-sign)를 인증하는 것이 가장 일반적인 선택이라고 믿고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-175">Based on the current research, it's generally believed that when the authentication and encryption steps are performed independently for non-AE modes of encryption, authenticating the ciphertext (encrypt-then-sign) is the best general option.</span></span> <span data-ttu-id="ffbd5-176">그러나 암호화에 대한 모든 정답은 없으며 이 일반화는 전문 암호 학자의 지시된 조언만큼 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-176">However, there's no one-size-fits-all correct answer to cryptography and this generalization isn't as good as directed advice from a professional cryptographer.</span></span>

<span data-ttu-id="ffbd5-177">메시징 형식을 변경할 수 없지만 인증되지 않은 CBC 암호 해독을 수행할 수 없는 응용 프로그램은 다음과 같은 완화 를 통합하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-177">Applications that are unable to change their messaging format but perform unauthenticated CBC decryption are encouraged to try to incorporate mitigations such as:</span></span>

- <span data-ttu-id="ffbd5-178">암호 해독기에서 패딩을 확인하거나 제거하지 않고 암호 해독:</span><span class="sxs-lookup"><span data-stu-id="ffbd5-178">Decrypt without allowing the decryptor to verify or remove padding:</span></span>
  - <span data-ttu-id="ffbd5-179">적용된 패딩은 여전히 제거하거나 무시해야 하므로 응용 프로그램에 부담을 덜어줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-179">Any padding that was applied still needs to be removed or ignored, you're moving the burden into your application.</span></span>
  - <span data-ttu-id="ffbd5-180">이점은 패딩 확인 및 제거를 다른 응용 프로그램 데이터 확인 논리에 통합할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-180">The benefit is that the padding verification and removal can be incorporated into other application data verification logic.</span></span> <span data-ttu-id="ffbd5-181">패딩 확인 및 데이터 확인을 일정한 시간에 수행할 수 있으면 위협이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-181">If the padding verification and data verification can be done in constant time, the threat is reduced.</span></span>
  - <span data-ttu-id="ffbd5-182">패딩을 해석하면 인식된 메시지 길이가 변경되므로 이 방법에서 방출되는 타이밍 정보가 여전히 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-182">Since the interpretation of the padding changes the perceived message length, there may still be timing information emitted from this approach.</span></span>
- <span data-ttu-id="ffbd5-183">암호 해독 패딩 모드를 ISO10126으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-183">Change the decryption padding mode to ISO10126:</span></span>
  - <span data-ttu-id="ffbd5-184">ISO10126 암호 해독 패딩은 PKCS7 암호화 패딩 및 ANSIX923 암호화 패딩과 모두 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-184">ISO10126 decryption padding is compatible with both PKCS7 encryption padding and ANSIX923 encryption padding.</span></span>
  - <span data-ttu-id="ffbd5-185">모드를 변경하면 전체 블록 대신 패딩 oracle 지식이 1바이트로 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-185">Changing the mode reduces the padding oracle knowledge to 1 byte instead of the entire block.</span></span> <span data-ttu-id="ffbd5-186">그러나 콘텐츠에 닫는 XML 요소와 같이 잘 알려진 바닥글이 있는 경우 관련 공격은 나머지 메시지를 계속 공격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-186">However, if the content has a well-known footer, such as a closing XML element, related attacks can continue to attack the rest of the message.</span></span>
  - <span data-ttu-id="ffbd5-187">또한 공격자가 동일한 일반 텍스트를 다른 메시지 오프셋으로 여러 번 암호화하도록 강제할 수 있는 상황에서는 일반 텍스트 복구를 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-187">This also doesn't prevent plaintext recovery in situations where the attacker can coerce the same plaintext to be encrypted multiple times with a different message offset.</span></span>
- <span data-ttu-id="ffbd5-188">타이밍 신호를 완화하기 위해 암호 해독 호출의 평가를 게이트:</span><span class="sxs-lookup"><span data-stu-id="ffbd5-188">Gate the evaluation of a decryption call to dampen the timing signal:</span></span>
  - <span data-ttu-id="ffbd5-189">보류 시간 계산은 패딩이 포함된 모든 데이터 세그먼트에 대해 암호 해독 작업이 걸리는 최대 시간을 초과해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-189">The computation of hold time must have a minimum in excess of the maximum amount of time the decryption operation would take for any data segment that contains padding.</span></span>
  - <span data-ttu-id="ffbd5-190">시간 계산은 [고해상도 타임스탬프 획득의](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps)지침에 따라 수행되어야 <xref:System.Environment.TickCount?displayProperty=nameWithType> 하며, (롤오버/오버플로에 따라) 두 개의 시스템 타임스탬프를 빼거나(NTP 조정 오류의 적용) 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-190">Time computations should be done according to the guidance in [Acquiring high-resolution time stamps](/windows/desktop/sysinfo/acquiring-high-resolution-time-stamps), not by using <xref:System.Environment.TickCount?displayProperty=nameWithType> (subject to roll-over/overflow) or subtracting two system timestamps (subject to NTP adjustment errors).</span></span>
  - <span data-ttu-id="ffbd5-191">시간 계산은 끝에 패딩뿐만 아니라 관리되는 응용 프로그램 또는 C++ 응용 프로그램의 모든 잠재적예외를 포함하여 암호 해독 작업을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-191">Time computations must be inclusive of the decryption operation including all potential exceptions in managed or C++ applications, not just padded onto the end.</span></span>
  - <span data-ttu-id="ffbd5-192">성공 또는 실패가 아직 결정되지 않은 경우 타이밍 게이트가 만료될 때 오류를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-192">If success or failure has been determined yet, the timing gate needs to return failure when it expires.</span></span>
- <span data-ttu-id="ffbd5-193">인증되지 않은 암호 해독을 수행하는 서비스에는 "잘못된" 메시지의 홍수가 들어왔는지 감지하기 위해 모니터링이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-193">Services that are performing unauthenticated decryption should have monitoring in place to detect that a flood of "invalid" messages has come through.</span></span>
  - <span data-ttu-id="ffbd5-194">이 신호는 거짓 긍정(합법적으로 손상된 데이터)과 거짓 부정(탐지를 회피하기에 충분한 시간 동안 공격을 분산)을 모두 전달한다는 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-194">Bear in mind that this signal carries both false positives (legitimately corrupted data) and false negatives (spreading out the attack over a sufficiently long time to evade detection).</span></span>

## <a name="finding-vulnerable-code---native-applications"></a><span data-ttu-id="ffbd5-195">취약한 코드 찾기 - 네이티브 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ffbd5-195">Finding vulnerable code - native applications</span></span>

<span data-ttu-id="ffbd5-196">Windows 암호화를 기반으로 빌드된 프로그램의 경우: 차세대(CNG) 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="ffbd5-196">For programs built against the Windows Cryptography: Next Generation (CNG) library:</span></span>

- <span data-ttu-id="ffbd5-197">암호 해독 호출은 플래그를 지정하는 [BCryptDecrypt입니다.](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt) `BCRYPT_BLOCK_PADDING`</span><span class="sxs-lookup"><span data-stu-id="ffbd5-197">The decryption call is to [BCryptDecrypt](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptdecrypt), specifying the `BCRYPT_BLOCK_PADDING` flag.</span></span>
- <span data-ttu-id="ffbd5-198">키 핸들은 BCRYPT_CHAINING_MODE [설정된](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) `BCRYPT_CHAIN_MODE_CBC` [BCryptSetProperty를](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) 호출하여 초기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-198">The key handle has been initialized by calling [BCryptSetProperty](/windows/desktop/api/bcrypt/nf-bcrypt-bcryptsetproperty) with [BCRYPT_CHAINING_MODE](/windows/desktop/SecCNG/cng-property-identifiers#BCRYPT_CHAINING_MODE) set to `BCRYPT_CHAIN_MODE_CBC`.</span></span>
  - <span data-ttu-id="ffbd5-199">`BCRYPT_CHAIN_MODE_CBC` 기본값이므로 영향을 받는 코드에 대한 `BCRYPT_CHAINING_MODE`값이 할당되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-199">Since `BCRYPT_CHAIN_MODE_CBC` is the default, affected code may not have assigned any value for `BCRYPT_CHAINING_MODE`.</span></span>

<span data-ttu-id="ffbd5-200">이전 Windows 암호화 API를 기반으로 빌드된 프로그램의 경우:</span><span class="sxs-lookup"><span data-stu-id="ffbd5-200">For programs built against the older Windows Cryptographic API:</span></span>

- <span data-ttu-id="ffbd5-201">암호 해독 호출은 을 사용하여 `Final=TRUE` [CryptDecrypt하는](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-201">The decryption call is to [CryptDecrypt](/windows/desktop/api/wincrypt/nf-wincrypt-cryptdecrypt) with `Final=TRUE`.</span></span>
- <span data-ttu-id="ffbd5-202">키 핸들은 KP_MODE [로](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) 설정된 [CryptSetKeyParam을](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) `CRYPT_MODE_CBC`호출하여 초기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-202">The key handle has been initialized by calling [CryptSetKeyParam](/windows/desktop/api/wincrypt/nf-wincrypt-cryptsetkeyparam) with [KP_MODE](/windows/desktop/api/wincrypt/nf-wincrypt-cryptgetkeyparam) set to `CRYPT_MODE_CBC`.</span></span>
  - <span data-ttu-id="ffbd5-203">`CRYPT_MODE_CBC` 기본값이므로 영향을 받는 코드에 대한 `KP_MODE`값이 할당되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-203">Since `CRYPT_MODE_CBC` is the default, affected code may not have assigned any value for `KP_MODE`.</span></span>

## <a name="finding-vulnerable-code---managed-applications"></a><span data-ttu-id="ffbd5-204">취약한 코드 찾기 - 관리되는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ffbd5-204">Finding vulnerable code - managed applications</span></span>

- <span data-ttu-id="ffbd5-205">암호 해독 호출은 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> 의 또는 <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> 메서드에 <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>대한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-205">The decryption call is to the <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor> or <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor(System.Byte[],System.Byte[])> methods on <xref:System.Security.Cryptography.SymmetricAlgorithm?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="ffbd5-206">여기에는 .NET 내의 다음 파생 형식이 포함되지만 타사 형식도 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-206">This includes the following derived types within the .NET, but may also include third-party types:</span></span>
    - <xref:System.Security.Cryptography.Aes>
    - <xref:System.Security.Cryptography.AesCng>
    - <xref:System.Security.Cryptography.AesCryptoServiceProvider>
    - <xref:System.Security.Cryptography.AesManaged>
    - <xref:System.Security.Cryptography.DES>
    - <xref:System.Security.Cryptography.DESCryptoServiceProvider>
    - <xref:System.Security.Cryptography.RC2>
    - <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
    - <xref:System.Security.Cryptography.Rijndael>
    - <xref:System.Security.Cryptography.RijndaelManaged>
    - <xref:System.Security.Cryptography.TripleDES>
    - <xref:System.Security.Cryptography.TripleDESCng>
    - <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>
- <span data-ttu-id="ffbd5-207">속성이 <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>로 설정되었습니다. <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType> <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ffbd5-207">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType>, <xref:System.Security.Cryptography.PaddingMode.ANSIX923?displayProperty=nameWithType>, or <xref:System.Security.Cryptography.PaddingMode.ISO10126?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="ffbd5-208"><xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> 기본값이므로 영향을 받는 코드는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> 속성을 할당하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-208">Since <xref:System.Security.Cryptography.PaddingMode.PKCS7?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Padding?displayProperty=nameWithType> property.</span></span>
- <span data-ttu-id="ffbd5-209">속성이 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType><xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ffbd5-209">The <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property was set to <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType></span></span>
  - <span data-ttu-id="ffbd5-210"><xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> 기본값이므로 영향을 받는 코드는 <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> 속성을 할당하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-210">Since <xref:System.Security.Cryptography.CipherMode.CBC?displayProperty=nameWithType> is the default, affected code may never have assigned the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode?displayProperty=nameWithType> property.</span></span>

## <a name="finding-vulnerable-code---cryptographic-message-syntax"></a><span data-ttu-id="ffbd5-211">취약한 코드 찾기 - 암호화 메시지 구문</span><span class="sxs-lookup"><span data-stu-id="ffbd5-211">Finding vulnerable code - cryptographic message syntax</span></span>

<span data-ttu-id="ffbd5-212">암호화된 콘텐츠가 AES의 CBC 모드를 사용하는 인증되지 않은 CMS EnvelopedData 메시지(2.16.840.1.1.1.1.1.2, 2.16.840.1.1.1.1.101.3.1.22, 2.16.840.1.1.1.101.3.4.42), DES(1.3.14.3.2.7), 3DES(1.2.840.113549.3.7) 또는 RC2(1.2.840.113549.3.2)는 CBC 모드에서 다른 블록 암호 알고리즘을 사용하는 메시지뿐만 아니라 취약합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-212">An unauthenticated CMS EnvelopedData message whose encrypted content uses the CBC mode of AES (2.16.840.1.101.3.4.1.2, 2.16.840.1.101.3.4.1.22, 2.16.840.1.101.3.4.1.42), DES (1.3.14.3.2.7), 3DES (1.2.840.113549.3.7) or RC2 (1.2.840.113549.3.2) is vulnerable, as well as messages using any other block cipher algorithms in CBC mode.</span></span>

<span data-ttu-id="ffbd5-213">스트림 암호는 이 특정 취약점에 취약하지 는 않지만 항상 ContentEncryptionAlgorithm 값을 검사하는 동안 데이터를 인증하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-213">While stream ciphers aren't susceptible to this particular vulnerability, Microsoft recommends always authenticating the data over inspecting the ContentEncryptionAlgorithm value.</span></span>

<span data-ttu-id="ffbd5-214">관리되는 응용 프로그램의 경우 CMS EnvelopedData Blob을 에 전달되는 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>모든 값으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-214">For managed applications, a CMS EnvelopedData blob can be detected as any value that is passed to <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.Decode(System.Byte[])?displayProperty=fullName>.</span></span>

<span data-ttu-id="ffbd5-215">네이티브 응용 프로그램의 경우 CMS EnvelopedData Blob은 [CryptMsgUpdate를](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) 통해 CMS 핸들에 [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) 제공된 `CMSG_ENVELOPED` 모든 값으로 검색할 수 있으며, 그 결과 CMSG_TYPE_PARAM 나중에 `CMSG_CTRL_DECRYPT` [CryptMsgControl을](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol)통해 명령을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-215">For native applications, a CMS EnvelopedData blob can be detected as any value provided to a CMS handle via [CryptMsgUpdate](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgupdate) whose resulting [CMSG_TYPE_PARAM](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsggetparam) is `CMSG_ENVELOPED` and/or the CMS handle is later sent a `CMSG_CTRL_DECRYPT` instruction via [CryptMsgControl](/windows/desktop/api/wincrypt/nf-wincrypt-cryptmsgcontrol).</span></span>

## <a name="vulnerable-code-example---managed"></a><span data-ttu-id="ffbd5-216">취약한 코드 예제 - 관리</span><span class="sxs-lookup"><span data-stu-id="ffbd5-216">Vulnerable code example - managed</span></span>

<span data-ttu-id="ffbd5-217">이 메서드는 쿠키를 읽고 해독하며 데이터 무결성 검사가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-217">This method reads a cookie and decrypts it and no data integrity check is visible.</span></span> <span data-ttu-id="ffbd5-218">따라서 이 메서드에서 읽는 쿠키의 내용은 쿠키를 받은 사용자 또는 암호화된 쿠키 값을 얻은 공격자에 의해 공격될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-218">Therefore, the contents of a cookie that is read by this method can be attacked by the user who received it, or by any attacker who has obtained the encrypted cookie value.</span></span>

```csharp
private byte[] DecryptCookie(string cookieName)
{
    HttpCookie cookie = Request.Cookies[cookieName];

    if (cookie == null)
    {
        return null;
    }

    using (ICryptoTransform decryptor = _aes.CreateDecryptor())
    using (MemoryStream memoryStream = new MemoryStream())
    using (CryptoStream cryptoStream =
        new CryptoStream(memoryStream, decryptor, CryptoStreamMode.Write))
    {
        byte[] readCookie = Convert.FromBase64String(cookie.Value);
        cryptoStream.Write(readCookie, 0, readCookie.Length);
        cryptoStream.FlushFinalBlock();
        return memoryStream.ToArray();
    }
}
```

## <a name="example-code-following-recommended-practices---managed"></a><span data-ttu-id="ffbd5-219">권장 사례에 따른 예제 코드 - 관리</span><span class="sxs-lookup"><span data-stu-id="ffbd5-219">Example code following recommended practices - managed</span></span>

<span data-ttu-id="ffbd5-220">다음 샘플 코드는 비표준 메시지 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-220">The following sample code uses a non-standard message format of</span></span>

`cipher_algorithm_id || hmac_algorithm_id || hmac_tag || iv || ciphertext`

<span data-ttu-id="ffbd5-221">`cipher_algorithm_id` 여기서 및 `hmac_algorithm_id` 알고리즘 식별자가 해당 알고리즘의 응용 프로그램 로컬(비표준) 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-221">where the `cipher_algorithm_id` and `hmac_algorithm_id` algorithm identifiers are application-local (non-standard) representations of those algorithms.</span></span> <span data-ttu-id="ffbd5-222">이러한 식별자는 맨 손으로 연결된 바이트 스트림이 아니라 기존 메시징 프로토콜의 다른 부분에서 의미가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-222">These identifiers may make sense in other parts of your existing messaging protocol instead of as a bare concatenated bytestream.</span></span>

<span data-ttu-id="ffbd5-223">또한 이 예제에서는 단일 마스터 키를 사용하여 암호화 키와 HMAC 키를 모두 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-223">This example also uses a single master key to derive both an encryption key and an HMAC key.</span></span> <span data-ttu-id="ffbd5-224">이는 싱어짐키 응용 프로그램을 이중 키 응용 프로그램으로 전환하고 두 키를 서로 다른 값으로 유지하는 데 편리함을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-224">This is provided both as a convenience for turning a singly-keyed application into a dual-keyed application, and to encourage keeping the two keys as different values.</span></span> <span data-ttu-id="ffbd5-225">또한 HMAC 키와 암호화 키가 동기화되지 않을 수 있음을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-225">It further guarantees that the HMAC key and encryption key can't get out of synchronization.</span></span>

<span data-ttu-id="ffbd5-226">이 샘플은 암호화 <xref:System.IO.Stream> 또는 암호 해독에 대한 a를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-226">This sample doesn't accept a <xref:System.IO.Stream> for either encryption or decryption.</span></span> <span data-ttu-id="ffbd5-227">현재 데이터 형식은 `hmac_tag` 값이 암호텍스트 앞에 있기 때문에 원 패스 암호화를 어렵게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-227">The current data format makes one-pass encrypt difficult because the `hmac_tag` value precedes the ciphertext.</span></span> <span data-ttu-id="ffbd5-228">그러나 이 형식은 파서를 더 단순하게 유지하기 위해 모든 고정 크기 요소를 처음에 유지하므로 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-228">However, this format was chosen because it keeps all of the fixed-size elements at the beginning to keep the parser simpler.</span></span> <span data-ttu-id="ffbd5-229">이 데이터 형식을 사용하면 구현자가 GetHashAndReset을 호출하고 TransformFinalBlock을 호출하기 전에 결과를 확인하라는 경고를 받지만 원 패스 암호 해독이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-229">With this data format, one-pass decrypt is possible, though an implementer is cautioned to call GetHashAndReset and verify the result before calling TransformFinalBlock.</span></span> <span data-ttu-id="ffbd5-230">스트리밍 암호화가 중요한 경우 다른 AE 모드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffbd5-230">If streaming encryption is important, then a different AE mode may be required.</span></span>

```csharp
// ==++==
//
//   Copyright (c) Microsoft Corporation.  All rights reserved.
//
//   Shared under the terms of the Microsoft Public License,
//   https://opensource.org/licenses/MS-PL
//
// ==--==

using System;
using System.Diagnostics;
using System.IO;
using System.Runtime.CompilerServices;
using System.Security.Cryptography;

namespace Microsoft.Examples.Cryptography
{
    public enum AeCipher : byte
    {
        Unknown,
        Aes256CbcPkcs7,
    }

    public enum AeMac : byte
    {
        Unknown,
        HMACSHA256,
        HMACSHA384,
    }

    /// <summary>
    /// Provides extension methods to make HashAlgorithm look like .NET Core's
    /// IncrementalHash
    /// </summary>
    internal static class IncrementalHashExtensions
    {
        public static void AppendData(this HashAlgorithm hash, byte[] data)
        {
            hash.TransformBlock(data, 0, data.Length, null, 0);
        }

        public static void AppendData(
            this HashAlgorithm hash,
            byte[] data,
            int offset,
            int length)
        {
            hash.TransformBlock(data, offset, length, null, 0);
        }

        public static byte[] GetHashAndReset(this HashAlgorithm hash)
        {
            hash.TransformFinalBlock(Array.Empty<byte>(), 0, 0);
            return hash.Hash;
        }
    }

    public static partial class AuthenticatedEncryption
    {
        /// <summary>
        /// Use <paramref name="masterKey"/> to derive two keys (one cipher, one HMAC)
        /// to provide authenticated encryption for <paramref name="message"/>.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="message">The message to encrypt</param>
        /// <returns>
        /// A concatenation of
        /// [cipher algorithm+chainmode+padding][mac algorithm][authtag][IV][ciphertext],
        /// suitable to be passed to <see cref="Decrypt"/>.
        /// </returns>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or bigger) value generated
        /// by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>.
        /// This implementation chooses to block deficient inputs by length, but does not
        /// make any attempt at discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase)
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Encrypt(byte[] masterKey, byte[] message)
        {
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (message == null)
                throw new ArgumentNullException(nameof(message));

            // First, choose an encryption scheme.
            AeCipher aeCipher = AeCipher.Aes256CbcPkcs7;

            // Second, choose an authentication (message integrity) scheme.
            //
            // In this example we use the master key length to change from HMACSHA256 to
            // HMACSHA384, but that is completely arbitrary. This mostly represents a
            // "cryptographic needs change over time" scenario.
            AeMac aeMac = masterKey.Length < 48 ? AeMac.HMACSHA256 : AeMac.HMACSHA384;

            // It's good to be able to identify what choices were made when a message was
            // encrypted, so that the message can later be decrypted. This allows for
            // future versions to add support for new encryption schemes, but still be
            // able to read old data. A practice known as "cryptographic agility".
            //
            // This is similar in practice to PKCS#7 messaging, but this uses a
            // private-scoped byte rather than a public-scoped Object IDentifier (OID).
            // Please note that the scheme in this example adheres to no particular
            // standard, and is unlikely to survive to a more complete implementation in
            // the .NET Framework.
            //
            // You may be well-served by prepending a version number byte to this
            // message, but may want to avoid the value 0x30 (the leading byte value for
            // DER-encoded structures such as X.509 certificates and PKCS#7 messages).
            byte[] algorithmChoices = { (byte)aeCipher, (byte)aeMac };
            byte[] iv;
            byte[] cipherText;
            byte[] tag;

            // Using our algorithm choices, open an HMAC (as an authentication tag
            // generator) and a SymmetricAlgorithm which use different keys each derived
            // from the same master key.
            //
            // A custom implementation may very well have distinctly managed secret keys
            // for the MAC and cipher, this example merely demonstrates the master to
            // derived key methodology to encourage key separation from the MAC and
            // cipher keys.
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
                using (ICryptoTransform encryptor = cipher.CreateEncryptor())
                {
                    // Since no IV was provided, a random one has been generated
                    // during the call to CreateEncryptor.
                    //
                    // But note that it only does the auto-generation once. If the cipher
                    // object were used again, a call to GenerateIV would have been
                    // required.
                    iv = cipher.IV;

                    cipherText = Transform(encryptor, message, 0, message.Length);
                }

                // The IV and ciphertest both need to be included in the MAC to prevent
                // tampering.
                //
                // By including the algorithm identifiers, we have technically moved from
                // simple Authenticated Encryption (AE) to Authenticated Encryption with
                // Additional Data (AEAD). By including the algorithm identifiers in the
                // MAC, it becomes harder for an attacker to change them as an attempt to
                // perform a downgrade attack.
                //
                // If you've added a data format version field, it can also be included
                // in the MAC to further inhibit an attacker's options for confusing the
                // data processor into believing the tampered message is valid.
                tagGenerator.AppendData(algorithmChoices);
                tagGenerator.AppendData(iv);
                tagGenerator.AppendData(cipherText);
                tag = tagGenerator.GetHashAndReset();
            }

            // Build the final result as the concatenation of everything except the keys.
            int totalLength =
                algorithmChoices.Length +
                tag.Length +
                iv.Length +
                cipherText.Length;

            byte[] output = new byte[totalLength];
            int outputOffset = 0;

            Append(algorithmChoices, output, ref outputOffset);
            Append(tag, output, ref outputOffset);
            Append(iv, output, ref outputOffset);
            Append(cipherText, output, ref outputOffset);

            Debug.Assert(outputOffset == output.Length);
            return output;
        }

        /// <summary>
        /// Reads a message produced by <see cref="Encrypt"/> after verifying it hasn't
        /// been tampered with.
        /// </summary>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <param name="cipherText">
        /// The output of <see cref="Encrypt"/>: a concatenation of a cipher ID, mac ID,
        /// authTag, IV, and cipherText.
        /// </param>
        /// <returns>The decrypted content.</returns>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="masterKey"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="ArgumentNullException">
        /// <paramref name="cipherText"/> is <c>null</c>.
        /// </exception>
        /// <exception cref="CryptographicException">
        /// <paramref name="cipherText"/> identifies unknown algorithms, is not long
        /// enough, fails a data integrity check, or fails to decrypt.
        /// </exception>
        /// <remarks>
        /// <paramref name="masterKey"/> should be a 128-bit (or larger) value
        /// generated by a secure random number generator, such as the one returned from
        /// <see cref="RandomNumberGenerator.Create()"/>. This implementation chooses to
        /// block deficient inputs by length, but doesn't make any attempt at
        /// discerning the randomness of the key.
        ///
        /// If the master key is being input by a prompt (like a password/passphrase),
        /// then it should be properly turned into keying material via a Key Derivation
        /// Function like PBKDF2, represented by Rfc2898DeriveBytes. A 'password' should
        /// never be simply turned to bytes via an Encoding class and used as a key.
        /// </remarks>
        public static byte[] Decrypt(byte[] masterKey, byte[] cipherText)
        {
            // This example continues the .NET practice of throwing exceptions for
            // failures. If you consider message tampering to be normal (and thus
            // "not exceptional") behavior, you may like the signature
            // bool Decrypt(byte[] messageKey, byte[] cipherText, out byte[] message)
            // better.
            if (masterKey == null)
                throw new ArgumentNullException(nameof(masterKey));
            if (masterKey.Length < 16)
                throw new ArgumentOutOfRangeException(
                    nameof(masterKey),
                    "Master Key must be at least 128 bits (16 bytes)");
            if (cipherText == null)
                throw new ArgumentNullException(nameof(cipherText));

            // The format of this message is assumed to be public, so there's no harm in
            // saying ahead of time that the message makes no sense.
            if (cipherText.Length < 2)
            {
                throw new CryptographicException();
            }

            // Use the message algorithm headers to determine what cipher algorithm and
            // MAC algorithm are going to be used. Since the same Key Derivation
            // Functions (KDFs) are being used in Decrypt as Encrypt, the keys are also
            // the same.
            AeCipher aeCipher = (AeCipher)cipherText[0];
            AeMac aeMac = (AeMac)cipherText[1];

            using (SymmetricAlgorithm cipher = GetCipher(aeCipher, masterKey))
            using (HMAC tagGenerator = GetMac(aeMac, masterKey))
            {
                int blockSizeInBytes = cipher.BlockSize / 8;
                int tagSizeInBytes = tagGenerator.HashSize / 8;
                int headerSizeInBytes = 2;
                int tagOffset = headerSizeInBytes;
                int ivOffset = tagOffset + tagSizeInBytes;
                int cipherTextOffset = ivOffset + blockSizeInBytes;
                int cipherTextLength = cipherText.Length - cipherTextOffset;
                int minLen = cipherTextOffset + blockSizeInBytes;

                // Again, the minimum length is still assumed to be public knowledge,
                // nothing has leaked out yet. The minimum length couldn't just be calculated
                // without reading the header.
                if (cipherText.Length < minLen)
                {
                    throw new CryptographicException();
                }

                // It's very important that the MAC be calculated and verified before
                // proceeding to decrypt the ciphertext, as this prevents any sort of
                // information leaking out to an attacker.
                //
                // Don't include the tag in the calculation, though.

                // First, everything before the tag (the cipher and MAC algorithm ids)
                tagGenerator.AppendData(cipherText, 0, tagOffset);

                // Skip the data before the tag and the tag, then read everything that
                // remains.
                tagGenerator.AppendData(
                    cipherText,
                    tagOffset + tagSizeInBytes,
                    cipherText.Length - tagSizeInBytes - tagOffset);

                byte[] generatedTag = tagGenerator.GetHashAndReset();

                // The time it took to get to this point has so far been a function only
                // of the length of the data, or of non-encrypted values (e.g. it could
                // take longer to prepare the *key* for the HMACSHA384 MAC than the
                // HMACSHA256 MAC, but the algorithm choice wasn't a secret).
                //
                // If the verification of the authentication tag aborts as soon as a
                // difference is found in the byte arrays then your program may be
                // acting as a timing oracle which helps an attacker to brute-force the
                // right answer for the MAC. So, it's very important that every possible
                // "no" (2^256-1 of them for HMACSHA256) be evaluated in as close to the
                // same amount of time as possible. For this, we call CryptographicEquals
                if (!CryptographicEquals(
                    generatedTag,
                    0,
                    cipherText,
                    tagOffset,
                    tagSizeInBytes))
                {
                    // Assuming every tampered message (of the same length) took the same
                    // amount of time to process, we can now safely say
                    // "this data makes no sense" without giving anything away.
                    throw new CryptographicException();
                }

                // Restore the IV into the symmetricAlgorithm instance.
                byte[] iv = new byte[blockSizeInBytes];
                Buffer.BlockCopy(cipherText, ivOffset, iv, 0, iv.Length);
                cipher.IV = iv;

                using (ICryptoTransform decryptor = cipher.CreateDecryptor())
                {
                    return Transform(
                        decryptor,
                        cipherText,
                        cipherTextOffset,
                        cipherTextLength);
                }
            }
        }

        private static byte[] Transform(
            ICryptoTransform transform,
            byte[] input,
            int inputOffset,
            int inputLength)
        {
            // Many of the implementations of ICryptoTransform report true for
            // CanTransformMultipleBlocks, and when the entire message is available in
            // one shot this saves on the allocation of the CryptoStream and the
            // intermediate structures it needs to properly chunk the message into blocks
            // (since the underlying stream won't always return the number of bytes
            // needed).
            if (transform.CanTransformMultipleBlocks)
            {
                return transform.TransformFinalBlock(input, inputOffset, inputLength);
            }

            // If our transform couldn't do multiple blocks at once, let CryptoStream
            // handle the chunking.
            using (MemoryStream messageStream = new MemoryStream())
            using (CryptoStream cryptoStream =
                new CryptoStream(messageStream, transform, CryptoStreamMode.Write))
            {
                cryptoStream.Write(input, inputOffset, inputLength);
                cryptoStream.FlushFinalBlock();
                return messageStream.ToArray();
            }
        }

        /// <summary>
        /// Open a properly configured <see cref="SymmetricAlgorithm"/> conforming to the
        /// scheme identified by <paramref name="aeCipher"/>.
        /// </summary>
        /// <param name="aeCipher">The cipher mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// A SymmetricAlgorithm object with the right key, cipher mode, and padding
        /// mode; or <c>null</c> on unknown algorithms.
        /// </returns>
        private static SymmetricAlgorithm GetCipher(AeCipher aeCipher, byte[] masterKey)
        {
            SymmetricAlgorithm symmetricAlgorithm;

            switch (aeCipher)
            {
                case AeCipher.Aes256CbcPkcs7:
                    symmetricAlgorithm = Aes.Create();
                    // While 256-bit, CBC, and PKCS7 are all the default values for these
                    // properties, being explicit helps comprehension more than it hurts
                    // performance.
                    symmetricAlgorithm.KeySize = 256;
                    symmetricAlgorithm.Mode = CipherMode.CBC;
                    symmetricAlgorithm.Padding = PaddingMode.PKCS7;
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            //
            // Since none of the symmetric encryption algorithms currently in .NET
            // support key sizes greater than 256-bit, we can use HMACSHA256 with
            // NIST SP 800-108 5.1 (Counter Mode KDF) to derive a value that is
            // no smaller than the key size, then Array.Resize to trim it down as
            // needed.

            using (HMAC hmac = new HMACSHA256(masterKey))
            {
                // i=1, Label=ASCII(cipher)
                byte[] cipherKey = hmac.ComputeHash(
                    new byte[] { 1, 99, 105, 112, 104, 101, 114 });

                // Resize the array to the desired keysize. KeySize is in bits,
                // and Array.Resize wants the length in bytes.
                Array.Resize(ref cipherKey, symmetricAlgorithm.KeySize / 8);

                symmetricAlgorithm.Key = cipherKey;
            }

            return symmetricAlgorithm;
        }

        /// <summary>
        /// Open a properly configured <see cref="HMAC"/> conforming to the scheme
        /// identified by <paramref name="aeMac"/>.
        /// </summary>
        /// <param name="aeMac">The message authentication mode to open.</param>
        /// <param name="masterKey">The master key from which other keys derive.</param>
        /// <returns>
        /// An HMAC object with the proper key, or <c>null</c> on unknown algorithms.
        /// </returns>
        private static HMAC GetMac(AeMac aeMac, byte[] masterKey)
        {
            HMAC hmac;

            switch (aeMac)
            {
                case AeMac.HMACSHA256:
                    hmac = new HMACSHA256();
                    break;
                case AeMac.HMACSHA384:
                    hmac = new HMACSHA384();
                    break;
                default:
                    // An algorithm we don't understand
                    throw new CryptographicException();
            }

            // Instead of using the master key directly, derive a key for our chosen
            // HMAC algorithm based upon the master key.
            // Since the output size of the HMAC is the same as the ideal key size for
            // the HMAC, we can use the master key over a fixed input once to perform
            // NIST SP 800-108 5.1 (Counter Mode KDF):
            hmac.Key = masterKey;

            // i=1, Context=ASCII(MAC)
            byte[] newKey = hmac.ComputeHash(new byte[] { 1, 77, 65, 67 });

            hmac.Key = newKey;
            return hmac;
        }

        // A simple helper method to ensure that the offset (writePos) always moves
        // forward with new data.
        private static void Append(byte[] newData, byte[] combinedData, ref int writePos)
        {
            Buffer.BlockCopy(newData, 0, combinedData, writePos, newData.Length);
            writePos += newData.Length;
        }

        /// <summary>
        /// Compare the contents of two arrays in an amount of time which is only
        /// dependent on <paramref name="length"/>.
        /// </summary>
        /// <param name="a">An array to compare to <paramref name="b"/>.</param>
        /// <param name="aOffset">
        /// The starting position within <paramref name="a"/> for comparison.
        /// </param>
        /// <param name="b">An array to compare to <paramref name="a"/>.</param>
        /// <param name="bOffset">
        /// The starting position within <paramref name="b"/> for comparison.
        /// </param>
        /// <param name="length">
        /// The number of bytes to compare between <paramref name="a"/> and
        /// <paramref name="b"/>.</param>
        /// <returns>
        /// <c>true</c> if both <paramref name="a"/> and <paramref name="b"/> have
        /// sufficient length for the comparison and all of the applicable values are the
        /// same in both arrays; <c>false</c> otherwise.
        /// </returns>
        /// <remarks>
        /// An "insufficient data" <c>false</c> response can happen early, but otherwise
        /// a <c>true</c> or <c>false</c> response take the same amount of time.
        /// </remarks>
        [MethodImpl(MethodImplOptions.NoInlining | MethodImplOptions.NoOptimization)]
        private static bool CryptographicEquals(
            byte[] a,
            int aOffset,
            byte[] b,
            int bOffset,
            int length)
        {
            Debug.Assert(a != null);
            Debug.Assert(b != null);
            Debug.Assert(length >= 0);

            int result = 0;

            if (a.Length - aOffset < length || b.Length - bOffset < length)
            {
                return false;
            }

            unchecked
            {
                for (int i = 0; i < length; i++)
                {
                    // Bitwise-OR of subtraction has been found to have the most
                    // stable execution time.
                    //
                    // This cannot overflow because bytes are 1 byte in length, and
                    // result is 4 bytes.
                    // The OR propagates all set bytes, so the differences are only
                    // present in the lowest byte.
                    result = result | (a[i + aOffset] - b[i + bOffset]);
                }
            }

            return result == 0;
        }
    }
}
```
