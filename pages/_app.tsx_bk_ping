
//import libraries
import '../styles/globals.css';
import React,{useMemo} from "react";
import { WalletAdapterNetwork} from "@solana/wallet-adapter-base" ;
 //walletmodalprovider will open some new screen for user to select wallets?
import { WalletModalProvider } from "@solana/wallet-adapter-react-ui" ;
import { 
  ConnectionProvider,
  WalletProvider
} from "@solana/wallet-adapter-react";

//
import{ PhantomWalletAdapter } from "@solana/wallet-adapter-wallets";

import { clusterApiUrl } from "@solana/web3.js";
require("@solana/wallet-adapter-react-ui/styles.css");
require("../styles/globals.css");
require("../styles/Home.module.css");

const App = ({Component,pageProps}) => {
  const network=WalletAdapterNetwork.Devnet
  //useMemo is a hook that loads stuff only one of the dependencies changes
  const endpoint=useMemo(() => clusterApiUrl(network),[network]);
  
  const wallets=useMemo(() => [ new PhantomWalletAdapter(),],[network]);
  
  return (
    <ConnectionProvider endpoint={endpoint}>
      <WalletProvider wallets={wallets} autoConnect>  
        <WalletModalProvider>
          <Component {...pageProps} />
        </WalletModalProvider>
      </WalletProvider>
    </ConnectionProvider>
  );//return

};//App

//function MyApp({ Component, pageProps }) {
//  return (  <Component {...pageProps} /> );
//}

//export default MyApp;
export default App;
