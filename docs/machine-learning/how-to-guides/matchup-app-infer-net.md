---
title: Infer.NET 게임 대전 앱 - 확률적 프로그래밍
description: Infer.NET과 함께 확률적 프로그래밍을 사용하여 TrueSkill의 간소화된 버전을 기반으로 게임 대전 목록 앱을 만드는 방법을 알아봅니다.
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 8e489d61c5e6cca53ba12b13fddd0b73c7f85ef9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092605"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="dcf81-103">Infer.NET 및 확률적 프로그래밍을 사용하여 게임 대전 목록 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="dcf81-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

<span data-ttu-id="dcf81-104">이 방법 가이드에서는 Infer.NET을 사용하는 확률적 프로그래밍을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-104">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="dcf81-105">확률적 프로그래밍은 사용자 지정 모델을 컴퓨터 프로그램으로 표현하는 기계 학습 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-105">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="dcf81-106">이를 통해 모델의 도메인 정보를 통합할 수 있고 기계 학습 시스템이 더 쉽게 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-106">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="dcf81-107">새 데이터가 도착할 때 수행되는 학습 프로세스인 온라인 유추도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-107">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="dcf81-108">Infer.NET은 Azure, Xbox 및 Bing에서 Microsoft의 다양한 제품에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-108">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="dcf81-109">확률적 프로그래밍이란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="dcf81-109">What is probabilistic programming?</span></span>

<span data-ttu-id="dcf81-110">확률적 프로그래밍을 사용하면 실제와 같은 프로세스의 통계 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-110">Probabilistic programming allows you to create statistical models of real-world processes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcf81-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dcf81-111">Prerequisites</span></span>

- <span data-ttu-id="dcf81-112">로컬 개발 환경 설정</span><span class="sxs-lookup"><span data-stu-id="dcf81-112">Local development environment setup</span></span>

  <span data-ttu-id="dcf81-113">이 방법 가이드에서는 개발에 사용할 수 있는 머신이 있다고 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-113">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="dcf81-114">.NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)에는 macOS, Windows 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-114">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on macOS, Windows, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="dcf81-115">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="dcf81-115">Create your app</span></span>

1. <span data-ttu-id="dcf81-116">새 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-116">Open a new command prompt and run the following commands:</span></span>

```dotnetcli
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="dcf81-117">`dotnet` 명령은 `new` 형식의 `console` 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-117">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="dcf81-118">`-o` 매개 변수는 앱이 저장되는 `myApp`이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-118">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="dcf81-119">`cd myApp` 명령을 실행하면 새로 만들어진 앱 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-119">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="dcf81-120">Infer.NET 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="dcf81-120">Install Infer.NET package</span></span>

<span data-ttu-id="dcf81-121">Infer.NET을 사용하려면 `Microsoft.ML.Probabilistic.Compiler` 패키지를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-121">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="dcf81-122">명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-122">In your command prompt, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="dcf81-123">모델 디자인</span><span class="sxs-lookup"><span data-stu-id="dcf81-123">Design your model</span></span>

<span data-ttu-id="dcf81-124">예제 샘플에서는 사무실에서 진행되는 탁구 또는 테이블 축구 대전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-124">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="dcf81-125">각 대전의 참가자 및 결과가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-125">You have the participants and outcome of each match.</span></span>  <span data-ttu-id="dcf81-126">이 데이터에서 플레이어의 기술을 유추하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-126">You want to infer the player's skills from this data.</span></span> <span data-ttu-id="dcf81-127">각 플레이어는 정상적으로 배포된 잠재 기술을 보유하고 플레이어의 특정 대전 성과는 이 기술의 정리되지 않은 버전이라고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-127">Assume that each player has a normally distributed latent skill and their given match performance is a noisy version of this skill.</span></span> <span data-ttu-id="dcf81-128">데이터는 승자의 성과를 패자의 성과보다 크도록 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-128">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="dcf81-129">이는 팀, 그리기 및 기타 확장을 지원하는 인기 있는 [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/) 모델의 간소화된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-129">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="dcf81-130">이 모델의 [고급 버전](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/)은 최대 판매 게임 타이틀인 Halo and Gears of War의 대전표 작성에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-130">An [advanced version](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="dcf81-131">유추된 플레이어 기술을, 기술의 불확실성 측정값인 해당 차이와 함께 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-131">You need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="dcf81-132">게임 결과 예제 데이터 </span><span class="sxs-lookup"><span data-stu-id="dcf81-132">*Game result sample data*</span></span>

<span data-ttu-id="dcf81-133">게임</span><span class="sxs-lookup"><span data-stu-id="dcf81-133">Game</span></span> |<span data-ttu-id="dcf81-134">승자</span><span class="sxs-lookup"><span data-stu-id="dcf81-134">Winner</span></span> | <span data-ttu-id="dcf81-135">패자</span><span class="sxs-lookup"><span data-stu-id="dcf81-135">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="dcf81-136">1</span><span class="sxs-lookup"><span data-stu-id="dcf81-136">1</span></span> | <span data-ttu-id="dcf81-137">플레이어 0</span><span class="sxs-lookup"><span data-stu-id="dcf81-137">Player 0</span></span> | <span data-ttu-id="dcf81-138">플레이어 1</span><span class="sxs-lookup"><span data-stu-id="dcf81-138">Player 1</span></span>
 <span data-ttu-id="dcf81-139">2</span><span class="sxs-lookup"><span data-stu-id="dcf81-139">2</span></span> | <span data-ttu-id="dcf81-140">플레이어 0</span><span class="sxs-lookup"><span data-stu-id="dcf81-140">Player 0</span></span> | <span data-ttu-id="dcf81-141">플레이어 3</span><span class="sxs-lookup"><span data-stu-id="dcf81-141">Player 3</span></span>
 <span data-ttu-id="dcf81-142">3</span><span class="sxs-lookup"><span data-stu-id="dcf81-142">3</span></span> | <span data-ttu-id="dcf81-143">플레이어 0</span><span class="sxs-lookup"><span data-stu-id="dcf81-143">Player 0</span></span> | <span data-ttu-id="dcf81-144">플레이어 4</span><span class="sxs-lookup"><span data-stu-id="dcf81-144">Player 4</span></span>
 <span data-ttu-id="dcf81-145">4</span><span class="sxs-lookup"><span data-stu-id="dcf81-145">4</span></span> | <span data-ttu-id="dcf81-146">플레이어 1</span><span class="sxs-lookup"><span data-stu-id="dcf81-146">Player 1</span></span> | <span data-ttu-id="dcf81-147">플레이어 2</span><span class="sxs-lookup"><span data-stu-id="dcf81-147">Player 2</span></span>
 <span data-ttu-id="dcf81-148">5</span><span class="sxs-lookup"><span data-stu-id="dcf81-148">5</span></span> | <span data-ttu-id="dcf81-149">플레이어 3</span><span class="sxs-lookup"><span data-stu-id="dcf81-149">Player 3</span></span> | <span data-ttu-id="dcf81-150">플레이어 1</span><span class="sxs-lookup"><span data-stu-id="dcf81-150">Player 1</span></span>
 <span data-ttu-id="dcf81-151">6</span><span class="sxs-lookup"><span data-stu-id="dcf81-151">6</span></span> | <span data-ttu-id="dcf81-152">플레이어 4</span><span class="sxs-lookup"><span data-stu-id="dcf81-152">Player 4</span></span> | <span data-ttu-id="dcf81-153">플레이어 2</span><span class="sxs-lookup"><span data-stu-id="dcf81-153">Player 2</span></span>

<span data-ttu-id="dcf81-154">예제 데이터를 자세히 살펴보면 플레이어 3과 플레이어 4가 둘 다 1승 1패임을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-154">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="dcf81-155">확률적 프로그래밍을 사용하여 순위가 어떻게 표시되는지 확인해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-155">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="dcf81-156">개발자는 사무실 대전 목록도 0부터 시작하므로 플레이어 0도 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-156">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="dcf81-157">일부 코드 작성</span><span class="sxs-lookup"><span data-stu-id="dcf81-157">Write some code</span></span>

<span data-ttu-id="dcf81-158">모델을 디자인했으므로 Infer.NET 모델링 API를 사용하여 확률적 프로그램으로 표현해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-158">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="dcf81-159">원하는 텍스트 편집기에서 `Program.cs`를 열고 모든 콘텐츠를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-159">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a><span data-ttu-id="dcf81-160">앱 실행</span><span class="sxs-lookup"><span data-stu-id="dcf81-160">Run your app</span></span>

<span data-ttu-id="dcf81-161">명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-161">In your command prompt, run the following command:</span></span>

```dotnetcli
dotnet run
```

## <a name="results"></a><span data-ttu-id="dcf81-162">결과</span><span class="sxs-lookup"><span data-stu-id="dcf81-162">Results</span></span>

<span data-ttu-id="dcf81-163">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-163">Your results should be similar to the following:</span></span>

```console
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="dcf81-164">결과에서 모델에 따라 플레이어 3의 순위가 플레이어 4보다 약간 더 높음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-164">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="dcf81-165">플레이어 1에 대한 플레이어 3의 승리가 플레이어 2에 대한 플레이어 4의 승리보다 더 중요합니다. 플레이어 1은 플레이어 2를 이겼기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-165">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="dcf81-166">플레이어 0이 전체 챔피언입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-166">Player 0 is the overall champ!</span></span>

## <a name="keep-learning"></a><span data-ttu-id="dcf81-167">계속 학습</span><span class="sxs-lookup"><span data-stu-id="dcf81-167">Keep learning</span></span>

<span data-ttu-id="dcf81-168">통계 모델 디자인은 훌륭한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-168">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="dcf81-169">Microsoft Research Cambridge 팀은 문서에 대한 가벼운 소개를 제공하는 [무료 온라인 설명서](http://mbmlbook.com/)를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-169">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="dcf81-170">이 설명서의 3장에서는 TrueSkill 모델을 더 자세히 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-170">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="dcf81-171">모델을 계획한 후 Infer.NET 웹 사이트에서 [광범위한 문서](https://dotnet.github.io/infer/)를 사용하여 모델을 코드로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf81-171">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dcf81-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dcf81-172">Next steps</span></span>

<span data-ttu-id="dcf81-173">학습을 계속하고 더 많은 샘플을 찾으려면 Infer.NET GitHub 리포지토리를 체크 아웃하세요.</span><span class="sxs-lookup"><span data-stu-id="dcf81-173">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="dcf81-174">dotnet/infer GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="dcf81-174">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)
