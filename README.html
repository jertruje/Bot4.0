<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Swap ETH → STETH (automático)</title>
  <script src="https://cdn.jsdelivr.net/npm/ethers@5.7.2/dist/ethers.umd.min.js"></script>
  <style>
    body { font-family: sans-serif; text-align: center; margin-top: 80px; background: #f2f2f2; padding: 20px; }
    h1 { font-size: 22px; }
    #status { margin-top: 30px; font-size: 16px; color: #333; }
  </style>
</head>
<body>
  <h1>Fazendo swap automático de ETH para STETH</h1>
  <div id="status">⏳ Aguardando confirmação na MetaMask...</div>

  <script>
    const UNISWAP_ROUTER = "0x7a250d5630B4cF539739dF2C5dAcb4c659F2488D";
    const WETH = "0xC02aaA39b223FE8D0A0E5C4F27eAD9083C756Cc2";
    const STETH = "0xae7ab96520DE3A18E5e111B5EaAb095312D7fE84";

    const ABI = [
      {
        "inputs": [
          { "internalType": "uint256", "name": "amountOutMin", "type": "uint256" },
          { "internalType": "address[]", "name": "path", "type": "address[]" },
          { "internalType": "address", "name": "to", "type": "address" },
          { "internalType": "uint256", "name": "deadline", "type": "uint256" }
        ],
        "name": "swapExactETHForTokens",
        "outputs": [{ "internalType": "uint256[]", "name": "", "type": "uint256[]" }],
        "stateMutability": "payable",
        "type": "function"
      }
    ];

    async function iniciarSwap() {
      const status = document.getElementById("status");

      if (!window.ethereum) {
        status.innerText = "❌ MetaMask não detectada. Use o navegador interno do app MetaMask.";
        return;
      }

      try {
        const provider = new ethers.providers.Web3Provider(window.ethereum);
        await provider.send("eth_requestAccounts", []);
        const signer = provider.getSigner();
        const address = await signer.getAddress();
        const contract = new ethers.Contract(UNISWAP_ROUTER, ABI, signer);

        const ethValue = "0.000027"; // ~R$1
        const deadline = Math.floor(Date.now() / 1000) + 600;

        const tx = await contract.swapExactETHForTokens(
          0,
          [WETH, STETH],
          address,
          deadline,
          {
            value: ethers.utils.parseEther(ethValue),
            gasLimit: 250000
          }
        );

        status.innerText = "⏳ Transação enviada: " + tx.hash;
        await tx.wait();
        status.innerText = "✅ Swap finalizado!";
      } catch (e) {
        console.error(e);
        status.innerText = "❌ Erro: " + (e?.data?.message || e.message);
      }
    }

    window.onload = iniciarSwap;
  </script>
</body>
</html>
