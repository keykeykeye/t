<!DOCTYPE html>

<html>

<head>

   <meta charset="UTF-8">

   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   <meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">
   <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />

   <title>Bulba</title>

<style>

    * {
        -webkit-user-drag: none;
        -webkit-user-modify: none;
        -webkit-highlight: none;
        touch-action: pan-x pan-y; 
        -webkit-touch-callout: none;
        -webkit-user-select: none;
        -khtml-user-select: none;
        -moz-user-select: none;
        -ms-user-select: none;
        -o-user-select: none;
        user-select: none;
    }

    

    @font-face {

        font-family: 'SSFont';
        font-display: block;
        src: url('SuperSedan.ttf') format('truetype');

    }

    body {

        max-width: 100%;

        width: 100%;

        max-height: 100vh;

        margin: 0 auto;

        overflow: hidden;

        background-color: #3a461f;

        font-family: 'SSFont';

        background-repeat: no-repeat;

        background-size: 100%;

        min-height: 100vh;

        position: relative;

        display: flex;

        align-items: center;

        justify-content: center;

    }



    .fon-sky {

        overflow: hidden;

        position: absolute;

        top: 0;

        left: 0;

        z-index: -1;

        width: 100%;

        height: 50vh;

        background: url(img/fon/sky.png);

        background-size: 100% 100%;

    }



    .fon-clouds-1 {

        position: absolute;

        top: 5%;

        left: 0;

        height: 40%;

        aspect-ratio: 883 / 279;

        background: url(img/fon/cloud_1.png) no-repeat;

        background-size: 100% auto;

        animation: clouds-move linear 20s infinite;

        transform: translateX(-100%) translateZ(0);

    }



    .fon-clouds-2 {

        position: absolute;

        top: 40%;

        left: 0;

        height: 50%;

        aspect-ratio: 68 / 27;

        background: url(img/fon/cloud_2.png) no-repeat;

        background-size: 100% auto;

        animation: clouds-move linear 20s infinite;

        animation-delay: 12s;

        transform: translateX(-100%);

    }   

    

    .fon-trees {

        position: absolute;

        height: 100%;

        width: 100%;

        left: 0;

        top: 0;

        background: url('img/fon/1.png') no-repeat;

        background-size: 100%;

        z-index: 1;

    }



    .fon-lawn {

        position: absolute;

        width: 100%;

        bottom: 0;

        height: 30vh;

        z-index: -1;

        background: url('img/fon/lawn.png') no-repeat;

        background-size: 100% 100%;

    }



    .fon-forest {

        position: absolute;

        bottom: 26vh;

        z-index: -1;

        width: 100%;

        height: 64vh;

        background: url('img/fon/forest.png') no-repeat;

        background-size: 100% auto;

    }



    .fon-tree {

        position: absolute;

        height: 92%;

        bottom: 20%;

        z-index: -1;

        right: -11%;

        aspect-ratio: 147 / 416;

        background: url('img/fon/tree-right.png') no-repeat;

        background-size: auto 100%;

    }



    .hits {

        position: absolute;

        top: 0;

        left: 0;

        height: 100%;

        width: 100%;

        overflow: hidden;

        z-index: 2;

    }

    

    .baldo {
        height: 990px;
        width: 668px;
        position: absolute;
        bottom: 15%;
        left: 50%;
        scale: 0.45;
        transform: translateX(-50%);
        transform-origin: bottom left;
    }



    .pen{
        position: absolute;
        height: 165px;
        width: 330px;
        background: url(img/pen.png) 0px 0px;
        /*animation: pen_play 0.7s steps(10) infinite;*/
        transform-origin: bottom left;
        scale: 0.7;
        transform: translateX(-47%);
        bottom: 8%;
        left: 50%;
    }



    .fon-grass {

        position: absolute;

        bottom: 0;

        width: 100%;

        height: 163px;

        overflow: hidden;

    }



    .fon-grass div{

        height: 100%;

        aspect-ratio: 538 / 513;

        position: absolute;

        background: url(img/fon/grass_1.gif) 0px 0px;

        background-size: auto 100%;

        bottom: -28px;

        z-index: 1;

    }



    .fon-grass-1{

        left: -12%;

    }



    .fon-grass-2{

        left: 15%;

    }



    .fon-grass-3{

        left: 38%;

    }



    .fon-grass-4{

        left: 63%;

    }

    

    .fon-grass-flower{

        width: 115px;

        aspect-ratio: 237 / 113;

        position: absolute;

        background: url(img/fon/flower.gif) 0px 0px no-repeat;

        background-size: 100%;

        bottom: 80px;

        left: 2%;

        z-index: 1;

    }

    

    .fon-grass-flower-2{

        height: 8vh;

        aspect-ratio: 237 / 124;

        position: absolute;

        background: url(img/fon/flower_2.gif) 0px 0px no-repeat;

        background-size: 100%;

        bottom: 17%;

        right: 7%;

        z-index: -1;

    }

    

    .fon-grass-flower-3 {

        height: 8vh;

        aspect-ratio: 153 / 80;

        position: absolute;

        background: url(img/fon/flower_3.gif) 0px 0px no-repeat;

        background-size: 100%;

        bottom: 21%;

        left: 13%;

        z-index: -1;

    } 

    .chock-infinity{
        height: 350px;
        width: 400px;
        position: absolute;
        transform-origin: bottom left;
        scale: 0.35;
        transform: translateX(-50%);
        background: url(img/chock_infinity.png) 0px 0px;
        background-size: inherit;
        left: 50%;
        bottom: 82%;
    }



    

    .chock-left-crack{

        height: 250px;

        width: 432px;

        position: fixed;

        zoom: 1.2;

        background: url(img/chock_crack.png) 0px 0px;

        bottom: 18%;

        left: -28%;

        overflow:hidden;

        visibility: hidden;

        /*animation: chock_left_crack_play 1s steps(58) infinite;*/

    }

    

    .chock-right-crack{

        height: 250px;

        width: 432px;

        position: fixed;

        zoom: 1.2;

        background: url(img/chock_crack.png) 0px 0px;

        bottom: 18%;

        right: -18%;

        transform: rotateY(180deg);

        overflow:hidden;

        visibility: hidden;

        /*animation: chock_right_crack_play 1s steps(58) infinite;*/

    }  

    .energy-bar{

        height: 141px;

        width: 312px;

        background: url(img/ui/energy_bar.png) 0px 0px;

        position: absolute;

        zoom: 0.55;

        top: 1%;

        left: 2%;

    }

    .energy-bar > text{

        font-family: 'SSFont';

        color: #321e06;

        mix-blend-mode: multiply;

        opacity: 0.5;

        position: absolute;

        right: 40px;

        bottom: 57px;

        font-size: 24px;

    }

    



    .counter-fon{

        height: 40px;

        width: 139px;

        background: url(img/ui/counter.png) 0px 0px no-repeat;

        background-size: cover;

        position: absolute;

        top: 4%;

        right: 0%;

    }

    

    .balance{

        font-family: 'SSFont';

        text-shadow: 2px 0px 0px #704918, -2px 0px 0px #704918, 0px 2px 0px #704918, 0px -2px 0px #704918;

        color: #d6b893;

        position: absolute;

        top: 3px;

        right: 14%;

        font-size: 25px;

        z-index: 2;

    }



    .bottom-bg-btns, .counter-fon, .energy-bar {

        z-index: 10;

    }

    

    .bottom-bg-btns{

        height: 82px;

        width: 95%;

        position: absolute;

        bottom: 10px;

        background: url(img/ui/panel_icons.png) 0px 0px no-repeat;

        background-size: 100%;

        background-blend-mode: multiply;

    }

    .bottom-btns {

        height: 83px;

        display: inline-block;

    }

    

    .upgrade{

        width: 29%;

    }

    

    .quests{

        width: 20%;

    }

    

    .guild{

        width: 22%;

    }

    

    .profile{

        width: 24%;

    }
    

    .hit{
        --translateX: 0px;
        --translateY: 0px;
        display: flex;
        align-items: center;
        position: absolute;
        transform: translate(var(--translateX), var(--translateY));
        gap: 1px;

        height: 6.5vw;

        animation: hit_play 1s linear forwards;
        z-index: -1;
    }

    .hit::before {
        content: "";
        width: 3.2vw;
        height: 3.2vw;
        background: url(img/hits/plus.png);
        background-size: 100% 100%;
    }

    .hit img {
        max-height: 100%;
    }

    

    

    .modal-profile-photo{

        background: url(https://sneg.top/uploads/posts/2023-06/1687465256_sneg-top-p-medved-na-avatarku-v-vatsap-dlya-muzhchin-10.jpg) 0px 0px no-repeat;

        background-size: 100%;

        /* position: absolute; */

        height: 87%;

        width: 70%;

        top: 4px;

        left: 17px;

        border-radius: 6px;

        box-shadow: 0 2px 2px rgba(0, 0, 0, 0.3);

    }

    

    

    .shake {

      animation: shake 0.3s cubic-bezier(.36,.07,.19,.97) both;

      transform: translate3d(0, 0, 0);

      backface-visibility: hidden;

      perspective: 1000px;

    }



    .clickable-area {

        position: fixed;

        top: 0;

        left: 0;

        right: 0;

        bottom: 0;

        z-index: 8;

    }



    .mining-overlay {

      display: none;

      position: fixed;

      z-index: 9;

      top: 0;

      left: 0;

      right: 0;

      bottom: 0;

    }



    .mining-overlay-time {

        display: none;

        position: absolute;

        left: 50%;

        bottom: 15%;

        text-wrap: nowrap;

        white-space: nowrap;

        transform: translateX(-45%);

        font-family: SSFont;

        font-size: 6vw;

        text-transform: uppercase;

        color: #d6b893;

        -webkit-text-stroke: 1px #704918;

        text-stroke: 1px #704918;

    }



    .mining-overlay-signboard {

        top: 0;

        left: 50%;

        transform: translateX(-50%);

        position: absolute;

        width: 90vw;

        aspect-ratio: 900 / 606;

        z-index: 5;

    }



    .mining-overlay-signboard::before {

        content: "";

        position: absolute;

        top: 0;

        left: 0;

        right: 0;

        bottom: 0;

        background: url(img/mining_signboard.gif);

        background-size: 100% auto;

    }



    .mining-overlay-signboard::after {

        content: "";

        position: absolute;

        top: 0;

        left: 0;

        right: 0;

        bottom: 0; 

        background: url(img/mining_signboard_shadow.gif);

        background-size: 100% auto;

        opacity: 0.5;

        z-index: -1;

    }

    
    @keyframes horizontal-shaking {
    0% { transform: translateX(0) }
    25% { transform: translateX(5px) }
    50% { transform: translateX(-5px) }
    75% { transform: translateX(5px) }
    100% { transform: translateX(0) }
    }
    

    @keyframes shake {

      10%, 90% {

        transform: translate3d(-1px, 0, 0);

      }

      

      20%, 80% {

        transform: translate3d(2px, 0, 0);

      }

    

      30%, 50%, 70% {

        transform: translate3d(-4px, 0, 0);

      }

    

      40%, 60% {

        transform: translate3d(4px, 0, 0);

      }

    }

        



    @keyframes clouds-move {

        0% {

            transform: translateX(-100vw) translateZ(0);

        }



        100% {

            transform: translateX(100vw) translateZ(0);

        }

    }

    

    

    

    @keyframes baldo_play {

        100% {

            background-position: -1500%;

        }

    }



    @keyframes baldo_going_sleep {

        100% {

            background-position: -10948px 0;

            bottom: 120px;

            transform: scale(0.23) translateX(31%);

        }

    }

    

    

    @keyframes baldo_idle_play {

        100% {

            background-position: -200%;

        }

    }



    @keyframes baldo_mining {

        100% {

            background-position: -200%;

        }

    }



    @keyframes baldo_to_mining {

        100% {

            background-position: -700%;

        }

    }


    @keyframes poof_play {

        0% { 

            opacity: 1;

        }

        100% {

            opacity: 0;

            display:none;

            background-position: -960px;

        }

    }

    

    

    @keyframes chock_left_crack_play {

        100% {

            background-position: -25056px;

        }

    }

    @keyframes chock_right_crack_play {

        100% {

            background-position: -25056px;

        }

    }

    

    

    

    @keyframes m_baldo_right_play{

        100% {

            background-position: -3780px;

        }

    }

    @keyframes pen_play{

        100% {

            background-position: -3300px;

        }

    }

    

    @keyframes chock_infinity_play{

        100% {

            background-position: -2900%;

        }

    }

    

    

    @keyframes hit_play{
        0% {
            opacity: 1;
            transform: translate(var(--translateX), var(--translateY));
        }

        15% {
            opacity: 1;
        }

        100% {
            transform: translate(calc(var(--translateX) + 100%), calc(var(--translateY) - 20vh));
            opacity: 0;
        }

    }

/*////////////////////////////////////////////////////////////////////////////*/

        

    #profile-modal {

        font-family: 'SSFont';

        border: none !important;

        outline: none;

        width: 85%;

        height: 91%;

        top: 0;

        background: url(img/ui/profile/fon.png) 0px 0px no-repeat;

        background-size: 100%;

        position: relative;

    }



    .profile-modal-body {

        padding: 11% 0 0;

        display: flex;

        flex-wrap: wrap;

    }

    

    .modal-profile-image {

        margin: 0 2vw 4.5vw 0;

        display: flex;

        align-items: center;

        justify-content: center;

        height: 21vw;

        aspect-ratio: 9 / 7;

        background: url(img/ui/profile/profile_image.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    

    .modal-name-profile {

        text-align: center;

        display: flex;

        align-items: center;

        justify-content: center;

        position: relative;

        height: 21vw;

        flex: 1;

    }

    

    .modal-name-profile > username {

        font-size: 7vw;

        color: #d6b893;

        -webkit-text-stroke: 1px #704918;

        text-stroke: 1px #704918;

    }





    .modal-baldo-earnings {

        margin: 0 0 10px;

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/profile/points_earnings.png) 0px 0px no-repeat;

        background-size: 100% auto;

    }

    

    .modal-referral-link {

        position: relative;

        margin: 0 0 13px;

        width: 100%;

        aspect-ratio: 724 / 149;

        background: url(img/ui/profile/referral_link.png) 0px 0px no-repeat;

        background-size: 100% auto;

        display: flex;

        padding: 13px 0 0px;

        box-sizing: border-box;

        align-items: center;

        justify-content: center;

        font-size: 5vw;

        text-transform: uppercase;

        color: rgba(104, 64, 35, 0.52);

    }

    .modal-referral-link-wrap {
        position: absolute;
        width: 100%;
        height: 100%;
        left: 0;
        top: 0;
    }

    .modal-referral-info {

        position: absolute;

        top: 0;

        right: 0;

        width: 9vw;

        height: 9vw;

        z-index: 5;

    }



    .modal-referral-info-popup {

        display: none;

        width: 100%;

        height: 100%;

        background-color: rgba(0, 0, 0, 0.3);

        position: fixed;

        top: 0px;

        left: 0px;

        z-index: 1;

    }



    .modal-referral-info-close {

        position: absolute;

        top: 0;

        right: 0;

        width: 14vw;

        height: 14vw;

    }



    .modal-referral-info-img {

        width: 90%;

        background-size: 100% auto;

        aspect-ratio: 809 / 382;

        position: absolute;

        top: 50%;

        left: 50%;

        background-image: url(img/ui/profile/referal_link_info.png);

        transform: translate(-50%, -50%);

    }

    

    .modal-referral-earnings {

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/profile/referral_earnings.png) 0px 0px no-repeat;

        background-size: 100% auto;

    }

    

    .modal-nazad {

        height: 18.7vw;

        width: 17.35%;

        left: 0%;

        aspect-ratio: 139 / 162;

        position: absolute;

        bottom: 0px;

        background: url(img/ui/profile/nazad.png) 0px 0px no-repeat;

        background-size: contain;

        overflow: visible;

    }

    .modal-profile-btn-profile {

        height: 18.7vw;

        left: 20%;

        aspect-ratio: 306 / 163;

        position: absolute;

        bottom: 0px;

        background: url(img/ui/profile/btns/profile_active.png) 0px 0px no-repeat;

        background-size: 100% auto;

        overflow: visible;

        

    }

    .modal-profile-btn-settings {

        height: 18.7vw;

        aspect-ratio: 306 / 163;

        left: 61.7%;

        position: absolute;

        bottom: 0px;

        background: url(img/ui/profile/btns/settings_passive.png) 0px 0px no-repeat;

        background-size: 100% auto;

        overflow: visible;

    }

    

    .settings-modal-body {

        padding: 11% 0 0;

    }



    .modal-settings-btn-profile {

        width: 100%;

        left: 19.3%;

        height: 75px;

        position: absolute;

        bottom: 0px;

        background: url(img/ui/profile/btns/profile_passive.png) 0px 0px no-repeat;

        background-size: 40%;

        overflow: visible;

    }

    .modal-settings-btn-settings {

        width: 100%;

        top: 87%;

        left: 59%;

        height: 75px;

        position: absolute;

        background: url(img/ui/profile/btns/settings_active.png) 0px 0px no-repeat;

        background-size: 40%;

        overflow: visible;

    }

    

    

    .modal-settings-music {

        margin: 0 0 10px;

        position: relative;

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/settings/music.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-settings-music > .music-switch {

        width: 115px;

        top: 50%;

        transform: translateY(-50%);

        right: 10px;

        aspect-ratio: 122 / 37;

        position: absolute;

        background: url(img/ui/settings/switch_on.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    

    .modal-settings-sound {

        margin: 0 0 10px;

        position: relative;

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/settings/sound.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-settings-clip {
        margin: 0 0 10px;

        position: relative;

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/settings/clip.png) 0px 0px no-repeat;

        background-size: 100%;
    }

    .modal-settings-clip > .clip-switch {

        width: 115px;

        top: 50%;

        transform: translateY(-50%);

        right: 10px;

        aspect-ratio: 122 / 37;

        position: absolute;

        background: url(img/ui/settings/switch_on.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-settings-sound > .sound-switch {

        width: 115px;

        top: 50%;

        transform: translateY(-50%);

        right: 10px;

        aspect-ratio: 122 / 37;

        position: absolute;

        background: url(img/ui/settings/switch_on.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    

    .modal-settings-language {

        margin: 0 0 10px;

        position: relative;

        width: 100%;

        aspect-ratio: 720 / 101;

        background: url(img/ui/settings/language.png) 0px 0px no-repeat;

        background-size: 100%;

    }



    .modal-settings-wiki {

        width: 30vw;

        aspect-ratio: 242 / 75;

        background: url(img/ui/settings/wiki.png) 0px 0px no-repeat;

        background-size: 100% auto;

        margin: 0 auto;

    }

/*//////////////////////////////////////////////////////////////////////////////////////////*/



    #wiki-modal {

        top: 0;

        left: 0;

        position: absolute;

        width: 100%;

        height: 100%;

        z-index: 100;

        background: #f9f9f9;

    }



    .wiki-modal-slide {

        display: none;

        position: absolute;

        left: 0;

        top: 0;

        width: 100%;

        height: 100%;

        background-repeat: no-repeat;

        background-position: center;

        background-size: contain;

    }



    .wiki-modal-slide.active {

        display: block; 

    }

    .wiki-modal-timeline {
        position: absolute;
        top: 4vw;
        left: 50%;
        z-index: 5;
        transform: translateX(-50%);
        width: 92%;
        height: 5px;
        display: flex;
    }

    .wiki-modal-timeline-item {
        margin-right: 7px;
        outline: 2px solid #000;
        border-radius: 16px;
        flex: 1;
        background: #fff;
        overflow: hidden;
    }
    
    .wiki-modal-timeline-progress {
        height: 100%;
        transition: width 5s linear;
        background: tomato;
    }

    .wiki-modal-timeline-item:last-child {
        margin: 0;
    }


    .wiki-modal-btn {

        position: absolute;

        width: 50%;

        height: 100%;

        z-index: 1;

        top: 0;

    }



    .wiki-modal-btn-prev {

        left: 0;

    }



    .wiki-modal-btn-next {

        right: 0;

    }

/*//////////////////////////////////////////////////////////////////////////////////////////*/

/*//////////////////////////////////////////////////////////////////////////////////////////*/

    #guild-modal{

        font-family: 'SSFont';

        border: none !important;

        outline: none;

        width: 100%;

        height: 100%;

        background: url(img/ui/squads/fon.png) 0px 0px no-repeat;

        background-size: 100% 98%;

        position: relative;

    }

    

    .modal-guild-main-btns {

        margin-left: auto;

        margin-right: auto;

        height: 83px;

        width: 81%;

        position: sticky;

        left: 19px;

    }

    

    .modal-guild-first {

        position: relative;

        top: 72px;

        left: 6px;

    }

    

    .join-squad {

        background: url(img/ui/squads/join_squad/join_clan.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    

    .create-squad {

        background: url(img/ui/squads/join_squad/create_clan_avalible.png) 0px 0px no-repeat;

        background-size: 100%;

    }



    .create-squad.closed {

        background-image: url(img/ui/squads/join_squad/create_clan_closed.png);

    }

    

    .modal-guild-create {

        position: relative;

        top: 72px;

        left: 6px;

    }

    

    .input-name-squad {

        padding: 0;

        margin-bottom: 10px;

        display: block;

        font-family: "SSFont";

        font-size: 9vw;

        color: #d6b893;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

        background: url(img/ui/squads/create_squad/clan_name_input.png) 0px 0px no-repeat;

        background-size: 100% 100%;

        text-align: center;

        width: 270px;

        height: 69px;

        border: 0;

    }



    .input-name-squad::placeholder {

        color: #d6b893;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

    }



    .input-name-squad:focus {

        outline: 0;

    }

    

    .caution-squad {

        background: url(img/ui/squads/create_squad/caution.png) 0px 0px no-repeat;

        background-size: contain;

        margin-bottom: 10px;

        width: 60vw;

        height: auto;

        aspect-ratio: 397 / 45;

    }

    

    .input-image-squad {

        display: block;

        background: url(img/ui/squads/create_squad/upload_squad_photo.png) 0px 0px no-repeat;

        background-size: 100% auto;

        width: 150px;

        height: auto;

        content-visibility: hidden;

        font-size: 0;

        aspect-ratio: 271 / 242;

    }



    #avatar-clan-upload {

        opacity: 0;

        position: absolute;

        appearance: none;

    }

    

    .btn-create-squad {

        background: url(img/ui/squads/create_squad/create_clan.png) 0px 0px no-repeat;

        background-size: contain;

        width: 175px;

        height: 72px;

        margin-top: 12px;

    }

    /*/////////////////////////////////////////////////////////////////////////////////////////////////////////*/

    

    .modal-guild-panel {

        

    }



    .squad-panel-wrapper {

        display: flex;

        flex-wrap: wrap;

        justify-content: center;

        margin: 10vh 8vw 0 12vw;

    }



    .squad-panel-logo {

        margin-right: 10px;

        width: 30%;

        aspect-ratio: 1 / 1;

        background: url(img/ui/squads/panel_squad/squad_logo.png);

        background-size: 100% 100%;

        border-radius: 25px;

        object-fit: contain;

    }



    .squad-panel-header {

        background: url(img/ui/squads/panel_squad/clan_name_block.png);

        background-size: 100% 100%;

        flex: 1;

        padding-left: 7vw;

        display: flex;

        justify-content: center;

        flex-direction: column;

    }



    .squad-panel-number {

        color: #916946;

    }



    .squad-panel-name {

        margin: -4px 0;

        color: #d6b893;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

        font-size: 10vw;

    }



    .squad-panel-count {

        font-size: 14px;

        color: #704918;

    }



    .squad-panel-earnings {

        width: 100%;

        aspect-ratio: 675 / 94;

        margin: 2vw 0;

        background: url(img/ui/squads/panel_squad/earnings.png) no-repeat;

        background-size: 100% auto;

        color: #d6b893;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

    }



    .leaderboard-squad-panel {

        position: relative;

        width: 90%;

        padding: 9vw 10px 0;

        margin-top: 10px;

        background: url(img/ui/squads/panel_squad/leaderboard_background.png);

        background-size: 100% 100%;

        border-radius: 16px;

    }

    

    .leaderboard-squad-heading {

        position: absolute;

        width: 60%;

        background: url(img/ui/squads/panel_squad/leaderboard_plaque.png) no-repeat;

        aspect-ratio: 361 / 85;

        top: -10px;

        left: 50%;

        transform: translateX(-50%);

        padding-top: 7px;

        display: flex;

        justify-content: center;

        text-transform: uppercase;

        font-size: 20px;

        color: #704918;

        background-size: 100% auto;

    }



    .leaderboard-squad-item {

        display: flex;

        align-items: center;

        padding: 0 20px;

        height: 10vw;

        margin-bottom: 1vw;

        background: url(img/ui/squads/panel_squad/leaderboard_item.png);

        background-size: 100% 100%;

        border-radius: 100px;

    }

    

    .leaderboard-squad-item:last-child {

        margin: 10px -10px 0;

        padding: 0 5px;

        background: none;

        border-radius: 16px;

    }



    .leaderboard-squad-number {

        font-size: 7vw;

        margin-right: 10px;

        color: #d6b893;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

    }



    .leaderboard-squad-avatar {

        height: 80%;

        aspect-ratio: 1 / 1;

        margin-right: 10px;

        outline: 1px solid #704918;

        border-radius: 50%;

    }



    .leaderboard-squad-name {

        font-size: 4.5vw;

        text-transform: uppercase;

        color: #d6b893;

        -webkit-text-stroke: 1px #704918;

        text-stroke: 1px #704918;

    }



    .leaderboard-squad-text {

        margin: -2px 0 0;

        font-size: 3vw;

        color: #704918;

    }



    .squad-panel-invite-link {

        background: url(img/ui/squads/panel_squad/clan_invite.png) 0px 0px no-repeat;

        background-size: 100% auto;

        margin-top: 12px;

        width: 90%;

        aspect-ratio: 641 / 75;

    }

    .squad-panel-leave-btn {

        background: url(img/ui/squads/panel_squad/leave_squad_btn.png) 0px 0px no-repeat;

        background-size: 100% auto;

        width: 70%;

        aspect-ratio: 239 / 28;

        margin: 5vw 0 0;

    }



    .modal-guild-list {

        padding: 15vh 8vw 0 11.5vw;

    }



    .squad-list-container {

        height: 60vh;

        overflow-y: scroll;

    }



    .squad-list-container::-webkit-scrollbar {

        display: none;

    }





    .squad-list-item {

        margin: 0 0 8px;

        height: 13vw;

        padding: 8px 2vw;

        display: flex;

        align-items: center;

        background: url(img/ui/squads/squads_list/item_background.png);

        background-size: 100% 100%;

    }



    .squad-list-ava {

        height: 100%;

        border-radius: 25px;

        aspect-ratio: 1 / 1;

        margin-right: 6px;

    }



    .squad-list-info {

        flex: 1;

    }



    .squad-list-name {

        font-size: 4.9vw;

        text-transform: uppercase;

        color: #d6b893;

        -webkit-text-stroke: 1px #704918;

        text-stroke: 1px #704918;

    }



    .squad-list-text {

        margin: -4px 0 1px;

        font-size: 2.8vw;

        text-transform: uppercase;

        color: #d6b893;

        text-shadow: 1px 0px 0px #704918, -1px 0px 0px #704918, 0px 1px 0px #704918, 0px -1px 0px #704918;

    }



    .squad-list-count {

        font-size: 2.6vw;

        color: #704918;

        text-transform: uppercase;

    }



    .squad-list-heading {

        position: absolute;

        width: 42vw;

        top: 6vh;

        left: 50%;

        font-size: 10vw;

        transform: translateX(-50%);

        background: url(img/ui/squads/squads_list/clans.png);

        background-size: 100% auto;

        aspect-ratio: 382 / 139;

    }



    .squad-list-btn-join {

        width: 20vw;

        margin-left: auto;

        background: url(img/ui/squads/squads_list/join.png);

        background-size: 100% auto;

        aspect-ratio: 37 / 15;

    }



    #quests-modal {

        font-family: 'SSFont';

        border: none !important;

        outline: none;

        width: 86%;

        height: 100%;

        background: url(img/ui/quests/fon.png) 0px 0px no-repeat;

        background-size: 100% 98%;

        position: relative;

    }



    .modal-quests-close, .modal-guild-close {

        width: 16vw;

        height: 16vw;

        position: absolute;

        top: 0;

        right: 0;

    }



    .modal-quests-btn-nazad, .modal-guild-btn-nazad {

        width: 13%;

        bottom: 10px;

        aspect-ratio: 139 / 162;

        left: 0;

    

        position: absolute;

        background: url(img/ui/profile/nazad.png) 0px 0px no-repeat;

        background-size: 100% auto;

        overflow: visible;

    }

    .modal-quests-btn-daily {

        width: 28%;

        bottom: 10px;

        aspect-ratio: 222 / 127;

        left: 14%;

        position: absolute;

        background: url(img/ui/quests/btns/daily_passive.png) 0px 0px no-repeat;

        background-size: 100% auto;

    }

    .modal-quests-btn-daily.disabled {
        background-image: url(img/ui/quests/btns/daily_disabled.png);
    }



    .modal-quests-btn-daily.active {

        background-image: url(img/ui/quests/btns/daily_active.png);

    }



    .modal-quests-btn-weekly {

        width: 28%;

        bottom: 10px;

        aspect-ratio: 222 / 127;

        left: 43%;

        position: absolute;

        background: url(img/ui/quests/btns/weekly_passive.png) 0px 0px no-repeat;

        background-size: 100% auto;

    }

    .modal-quests-btn-weekly.disabled {
        background-image: url(img/ui/quests/btns/weekly_disabled.png);
    }

    .modal-quests-btn-weekly.active {

        background-image: url(img/ui/quests/btns/weekly_active.png);

    }

    

    .modal-quests-btn-main {

        width: 28%;

        bottom: 10px;

        aspect-ratio: 222 / 127;

        left: 72%;

        position: absolute;

        background: url(img/ui/quests/btns/main_passive.png) 0px 0px no-repeat;

        background-size: 100% auto;

    }



    .modal-quests-btn-main.active {

        background-image: url(img/ui/quests/btns/main_active.png);

    }



    .modal-quests-list {
        overflow: scroll;
        height: 69vh;
        margin: 22vw 5vw 0 3vw;
    }



    .modal-quests-item {
        position: relative;

        height: 18vw;

        padding: 5px 10px;

        margin: 0 0 10px;

        background: url(img/ui/quests/item/item_background.png);

        background-size: 100% 100%;

        display: flex;

        align-items: center;

    }

    .modal-quests-item-wrapper {
        display: flex;
        flex-direction: column;
        height: 100%;
    }

    .modal-quests-item-link-wrap {
        position: absolute;
        z-index: 2;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
    }



    .modal-quests-item-completed .modal-quests-item-btn {

        background-image: url(img/ui/quests/item/task_completed.png) !important;
        z-index: 2;

    }

    .modal-quests-item-check .modal-quests-item-btn {
        position: relative;
        z-index: 3;
        background-image: url(img/ui/quests/item/check_task.png);
    }


    .modal-quests-item-img {

        height: 75%;

        aspect-ratio: 1 / 1;

        margin-right: 10px;

    }



    .modal-quests-item-text {

        margin: 2vw 0 5px;

        text-transform: uppercase;

        font-size: 3.5vw;

        color: #d6b893;

        -webkit-text-stroke: 1px #704918;

        text-stroke: 1px #704918;

    }



    .modal-quests-item-btn {
        margin: auto 0 2vw;

        display: block;

        width: 38vw;

        aspect-ratio: 302 / 41;

        background: url(img/ui/quests/item/complete_task.png) no-repeat;

        background-size: contain;

    }



/*//////////////////////////////////////////////////////////////////////////////////////////*/

/*//////////////////////////////////////////////////////////////////////////////////////////*/

/*//////////////////////////////////////////////////////////////////////////////////////////*/



    #upgrade-modal {

        font-family: 'SSFont';

        border: none !important;

        outline: none;

        width: 100%;

        height: 100%;

        background: url(img/ui/upgrade/fon.png) 0px 0px no-repeat;

        background-size: 100% 98%;

        position: relative;

    }

    

    .boosts-modal-body {

        top: 40px;

        position: relative;

    }

    

    .confirm-boost{

        width: 100%;

        height: 100%;

        /* background: url(img/ui/upgrade/boosts/confirm_bone.png) 0px 0px no-repeat; */

        background-color: rgba(0, 0, 0, 0.3);

        background-size: 100%;

        position: fixed;

        top: 0px;

        left: 0px;

        z-index: 1;

        display: none;

    }

    .confirm-boost-close {

        top: 0;

        right: 0;

        width: 100px;

        height: 100px;

        position: absolute;

    }



    .confirm-boost-img {

        width: 100%;

        background-size: 100% auto;

        aspect-ratio: 450 / 247;

        position: absolute;

        top: 50%;

        left: 50%;

        transform: translate(-50%, -50%);

    }



    .confirm-boost-close-overlay {

        position: absolute;

        z-index: -1;

        top: 0;

        left: 0;

        right: 0;

        bottom: 0;

    }



    .confirm-boost-confirm{

        bottom: 2%;

        left: 50%;

        transform: translateX(-50%);

        width: 39vw;

        height: 63px;

        position: absolute;

    }

    

    .modal-boosts {

        margin-left: auto;

        margin-right: auto;

        width: 92%;

        aspect-ratio: 755 / 238;

        position: sticky;

        background-position: 0 0;

        background-repeat: no-repeat;

        background-size: 100% auto;

    }

    .boost-bone {

        background-image: url(img/ui/upgrade/boosts/bone.png);

    }

    .boost-coffee {

        background-image: url(img/ui/upgrade/boosts/coffee.png);

    }

    .boost-energy-drink {

        background-image: url(img/ui/upgrade/boosts/energy_drink.png);

    }

    .boost-steak {

        background-image: url(img/ui/upgrade/boosts/steak.png);

    }



    .boosts-ebaldo-wrap, .upgrades-ebaldo-wrap {

        box-sizing: border-box;

        padding: 0 3vw;

        min-width: 18vw;

        height: 7vw;

        position: absolute;

        display: flex;

        align-items: center;

        justify-content: center;

        right: 8%;

        background: url(img/ui/upgrade/price.png); 

        background-size: 100% 100%;

    }



    .boosts-ebaldo-wrap {

        bottom: 5%;

    }



    .boosts-ebaldo-wrap.not, .upgrades-ebaldo-wrap.not {

        background-image: url(img/ui/upgrade/price_not.png);

    }

    .boosts-ebaldo-wrap.unavailable, .upgrades-ebaldo-wrap.unavailable {

        background-image: url(img/ui/upgrade/price_unavailable.png) !important;

    }



    .boosts-ebaldo {

        font-size: 2.3vw;

        color: #231c15;

        opacity: 0.7;

        mix-blend-mode: multiply;

    }



    .boosts-available {

        position: absolute;

        left: 32.2%;

        bottom: 27%;

        mix-blend-mode: multiply;

        color: #704918;

        font-size: 2vw;

    }

    

    .upgrades-modal-body {

        top: 40px;

        position: relative;

    }



    .modal-boosts-unavailable, .modal-upgrades-unavailable {

        position: sticky;

        margin: 0 auto;

        background-repeat: no-repeat;

        background-size: contain;

        mix-blend-mode: multiply;

    }



    .modal-upgrades-unavailable {

        background-image: url(img/ui/upgrade/upgrades/unavailable_message.png);

        width: 77%;

        aspect-ratio: 625 / 57;

    }



    .modal-boosts-unavailable {

        background-image: url(img/ui/upgrade/boosts/unavailable_message.png);

        width: 70%;

        aspect-ratio: 173 / 19;

    }



    

    .modal-upgrades {

        width: 92%;

        margin: 0 auto;

        position: sticky;

        aspect-ratio: 54 / 17;

    }



    .upgrades-axe {

        background: url(img/ui/upgrade/upgrades/axe.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-upgrades-axe-animate {

        width: 21vw;

        left: 4vw;

        top: 50%;

        aspect-ratio: 30 / 23;

        transform: translateY(-60%);

        position: absolute;

        background: url(img/ui/upgrade/upgrades/axe.gif) 0px 0px no-repeat;

        background-size: 100%;

    }

    

    .upgrades-energy {

        background: url(img/ui/upgrade/upgrades/energy.png) 0px 0px no-repeat;

        background-size: 100%;

    }



    .modal-upgrades-energy-animate {

        width: 12vw;

        left: 9vw;

        top: 50%;

        transform: translateY(-46%);

        aspect-ratio: 300 / 403;

        position: absolute;

        background: url(img/ui/upgrade/upgrades/energy.gif) 0px 0px no-repeat;

        background-size: 85%;

    }

    

    .upgrades-mining {

        background: url(img/ui/upgrade/upgrades/mining.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-upgrades-mining-animate {

        width: 15vw;

        left: 6vw;

        top: 50%;

        transform: translateY(-53%);

        position: absolute;

        background: url(img/ui/upgrade/upgrades/mining.gif) 0px 0px no-repeat;

        background-size: 100%;

        aspect-ratio: 1 / 1;

    }

    .upgrades-lvl {

        position: absolute;

        top: 23.2%;

        padding: 1vw 2vw;

        font-size: 2.2vw;

        color: rgba(12, 7, 3, 0.6);

        background: url(img/ui/upgrade/upgrades/level.png);

        background-size: 100% 100%;

    }



    .upgrades-axe .upgrades-lvl {

        left: 47.1%;

    }



    .upgrades-energy .upgrades-lvl {

        left: 58.8%;

    }



    .upgrades-mining .upgrades-lvl {

        left: 58.9%;

    }

    .upgrades-ebaldo {

        font-size: 2.3vw;

        color: #231c15;

        opacity: 0.7;

        mix-blend-mode: multiply;

    }



    .upgrades-ebaldo-wrap {

        bottom: 5%;

    }



    .modal-upgrade-btn-nazad {

        height: 18.7vw;

        bottom: 2.6%;

        left: 4.1%;

        aspect-ratio: 139 / 162;

        position: absolute;

        background: url(img/ui/upgrade/btns/nazad.png) 0px 0px no-repeat;

        background-size: 100%;

        overflow: visible;

    }

    .modal-upgrade-btn-upgrades {

        height: 18.7vw;

        bottom: 2.6%;

        left: 22.6%;

        aspect-ratio: 321 / 169;

        position: absolute;

        background: url(img/ui/upgrade/btns/upgrades_active.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .modal-upgrade-btn-boosts {

        height: 18.7vw;

        aspect-ratio: 321 / 169;

        bottom: 2.6%;

        left: 61%;

        position: absolute;

        background: url(img/ui/upgrade/btns/boosts_passive.png) 0px 0px no-repeat;

        background-size: 100%;

    }

    .not-supported {
        position: fixed;
        width: 100%;
        height: 100%;
        display: none;
        align-items: center;
        justify-content: center;
        z-index: 200;
        background: url(img/ui/loading/background.jpg) no-repeat;
        background-size: cover;
        background-color: #3a461f;
        color: #d6b893;
        font-size: 10vw;
        -webkit-text-stroke: 2px #704918;
        text-stroke: 2px #704918;
        text-align: center;
    }

    .loading-foliage {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: url(img/ui/loading/foliage.gif);
        background-size: cover;
        z-index: 101;
    }

    .loading {

        position: fixed;

        display: flex;

        flex-direction: column;

        justify-content: center;

        top: 0;

        left: 0;

        width: 100%;

        height: 100%;

        z-index: 100;

        background: url(img/ui/loading/background.jpg) no-repeat;

        background-size: cover;

        background-color: #3a461f;

        color: #d6b893;

    }



    .loading-heading {

        margin: 0 0 5vw;

        font-size: 10vw;

        padding-left: 26vw;

        -webkit-text-stroke: 2px #704918;

        text-stroke: 2px #704918;

    }



    .loading-item {
        position: relative;
        padding-left: 30vw;
        margin: 0 0 2.5vw;
        font-size: 3.9vw;
        -webkit-text-stroke: 1px #704918;
        opacity: 0.7;
        text-stroke: 1px #704918;
    }


    .loading-item::before {

        position: absolute;

        top: 50%;

        transform: translateY(-50%);

        left: 22vw;

        width: 5vw;

        height: 5vw;

        content: "";

        background: url(img/ui/loading/undone.png) no-repeat;

        background-size: 100% 100%;

    }

    .loading-item.done {

        opacity: 1;

    }



    .loading-item.done::before {

        background-image: url('img/ui/loading/done.png');

    }

    .dots::after {

        position: absolute;

        content: '';

        display: inline-block;

        animation: dots 1s steps(4, end) infinite;

    }



    .loading-dogs {

        margin: 3vw auto 0;

        height: 225px;

        width: 535px;

        zoom: 0.6;

        background: url(img/ui/loading/dogs-preview.png);

    }

    .loading-item.done + .loading-item {
        animation: loading_item_pulse 1.5s infinite;
    }


    @keyframes loading_item_pulse {
        50% {
            opacity: 1;
        }

        100% {
            opacity: 0.7;
        }
    }

    @keyframes dogs_loading {

        0% {

            background-position: 0;

        }



        100% {

            background-position: -16050px;

        }

    }



    @keyframes dots {

        0%, 20% {

            content: '';

        }



        40% {

            content: '.';

        }

        60% {

            content: '..';

        }

        80%, 100% {

            content: '...';

        }

    }

    .reconnect {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 15;
        background: rgba(0, 0, 0, 0.6);
        display: none;
        flex-direction: column;
        align-items: center;
        padding: 37vh 0 0;
    }

    .reconnect-title {
        top: 50%;
        left: 50%;
        font-size: 11.5vw;
        color: #d6b893;
        -webkit-text-stroke: 2px #704918;
        text-stroke: 2px #704918;
    }

    .reconnect-timer {
        color: #d6b893;
        -webkit-text-stroke: 2px #704918;
        text-stroke: 2px #704918;
        font-size: 7vw;
    }

    .reconnect-counter {
        color: #d6b893;
        -webkit-text-stroke: 2px #704918;
        text-stroke: 2px #704918;
        font-size: 7vw;
    }

    .videoplayer {
        position: absolute;
        width: 23vw;
        height: 35vw;
        background: #f9f9f9;
        box-shadow: 0px 0px 20px 7px rgba(0, 0, 0, 0.3);
        top: 100px;
        left: 5vw;
        z-index: 11;
        border-radius: 10px;
        overflow: hidden;
        transition: left 0.5s ease, top 0.5s ease;
    }

    .videoplayer iframe {
        width: 100%;
        height: 100%;
        pointer-events: none;
    }

    

</style>



</head>

<body>
    <div class="not-supported">
        Sorry! Your device is not supported
    </div>
    <script>
        if (typeof HTMLDialogElement === 'undefined' || !('showModal' in HTMLDialogElement.prototype)) {
            document.querySelector('.not-supported').style.display = 'flex';
        } 
    </script>
    <div class="loading-foliage">
    </div>
    <div class="loading">

        <div class="loading-heading">Loading<span class="dots"></span></div>

        <div class="loading-item done">official game demo</div>

        <div class="loading-item">clan system</div>

        <div class="loading-item">new skins and upgrades</div>

        <div class="loading-item">new locations</div>

        <div class="loading-item">special events</div>

        <div class="loading-item">clan battles</div>

        <div class="loading-item" style="font-size: 6vw;">airdrop</div>

        <div class="loading-item">staking</div>

        <div class="loading-dogs"></div>

    </div>
    <div class="reconnect">
        <div class="reconnect-title">reconnect<span class="dots"></span></div>
        <div class="reconnect-timer">00:05</div>
        <div class="reconnect-counter">Failed requests: <span></span></div>
    </div>

    <script>
        const reconnectElement = document.querySelector('.reconnect');
        const reconnectCounter = document.querySelector('.reconnect-counter span');
        const reconnectTimer = document.querySelector('.reconnect-timer');

        function startReconnectTimer() {
            let timer = 5;
            reconnectTimer.textContent = `00:${timer.toString().padStart(2, '0')}`;
            
            const intervalId = setInterval(() => {
                timer--;
                reconnectCounter.textContent = global_click_queue;
                reconnectTimer.textContent = `00:${timer.toString().padStart(2, '0')}`;

                if (timer <= 0) {
                    clearInterval(intervalId);
                    if (global_click_queue === 0) {
                        reconnectElement.style.display = 'none';
                    } else {
                        location.reload();
                    }
                }
            }, 1000);
        }

        function checkAndReconnect() {
            if (global_click_queue !== 0) {
                reconnectElement.style.display = 'flex';
                reconnectCounter.textContent = global_click_queue;
                startReconnectTimer();
            }
        }
    </script>

    <script>
        const spriteLoading = new Image();
        spriteLoading.src = 'img/ui/loading/dogs.png';
        spriteLoading.addEventListener('load', function() {
            document.querySelector('.loading-dogs').style.backgroundImage = 'url(img/ui/loading/dogs.png)';
            document.querySelector('.loading-dogs').style.animation = 'dogs_loading 1s steps(30) infinite';
        })
        let minimumTimeElapsed = false;
        let resourcesLoaded = false;
        setTimeout(function() {
            minimumTimeElapsed = true;
            if (resourcesLoaded) {
                hideLoadingElement();
            }
        }, 15000);

        function hideLoadingElement() {
            document.querySelector('.loading-foliage').style.display = 'block';
            document.querySelector('.loading').style.display = 'none';
            setTimeout(() => {
                document.querySelector('.loading-foliage').style.display = 'none';
            }, 1200)
        }

        window.addEventListener('load', function() {
            resourcesLoaded = true;
            if (minimumTimeElapsed) {
                hideLoadingElement();
            }
        });
    </script>

    <div class="mining-overlay">

        <div class="mining-overlay-signboard">

            <div class="mining-overlay-time">00:00:00 left</div>

        </div>

    </div>

    <div class="clickable-area"></div>

    <div class="energy-bar">

        <text><now-energy-text>100</now-energy-text>/<max-energy-text>100</max-energy-text></text>

    </div>

    <div class="counter-fon">

        <div class="balance">0</div>

    </div>

    <!-- <div class="videoplayer">
    </div>
    <script>
        const videoplayer = document.querySelector('.videoplayer');

        if(localStorage.getItem("clip_mode") == "off") {
            videoplayer.style.display = 'none';
        }

        const videoLinks = [
            'http://www.youtube.com/embed?listType=playlist&list=PLthjD69EpGSZKhmQzUOZfUhCZzDs1IBBz'
        ];

        let currentIndex = 0;

        function updateVideo() {
            const currentVideo = videoLinks[currentIndex];
            videoplayer.innerHTML = `<iframe src="${currentVideo}&autoplay=1&mute=1&modestbranding=1&controls=0" allow="autoplay" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
            currentIndex = (currentIndex + 1) % videoLinks.length;
        }

        window.onload = updateVideo;

        let isDragging = false;
        let startX, startY, initialX, initialY;

        const boundaryTop = 100;
        const boundaryLeft = 15;
        const boundaryRight = window.innerWidth - 15;
        const boundaryBottom = window.innerHeight - 100;

        videoplayer.addEventListener('touchstart', function(e) {
            isDragging = true;
            const touch = e.touches[0];
            startX = touch.clientX;
            startY = touch.clientY;
            initialX = videoplayer.offsetLeft;
            initialY = videoplayer.offsetTop;
            e.preventDefault();
        }, { passive: false });

        videoplayer.addEventListener('touchmove', function(e) {
            if (isDragging) {
                const touch = e.touches[0];
                const dx = touch.clientX - startX;
                const dy = touch.clientY - startY;

                let newLeft = initialX + dx;
                let newTop = initialY + dy;

                if (newLeft < boundaryLeft) {
                    newLeft = boundaryLeft;
                } else if (newLeft + videoplayer.offsetWidth > boundaryRight) {
                    newLeft = boundaryRight - videoplayer.offsetWidth;
                }

                if (newTop < boundaryTop) {
                    newTop = boundaryTop;
                } else if (newTop + videoplayer.offsetHeight > boundaryBottom) {
                    newTop = boundaryBottom - videoplayer.offsetHeight;
                }

                videoplayer.style.left = `${newLeft}px`;
                videoplayer.style.top = `${newTop}px`;

                e.preventDefault();
            }
        }, { passive: false });

        videoplayer.addEventListener('touchend', function() {
            if (!isDragging) return;
            isDragging = false;

            const currentLeft = videoplayer.offsetLeft;
            const currentTop = videoplayer.offsetTop;

            const distances = {
                topLeft: Math.sqrt(currentLeft**2 + currentTop**2),
                topRight: Math.sqrt((boundaryRight - videoplayer.offsetWidth - currentLeft)**2 + currentTop**2),
                bottomLeft: Math.sqrt(currentLeft**2 + (boundaryBottom - videoplayer.offsetHeight - currentTop)**2),
                bottomRight: Math.sqrt((boundaryRight - videoplayer.offsetWidth - currentLeft)**2 + (boundaryBottom - videoplayer.offsetHeight - currentTop)**2)
            };

            const closestCorner = Object.keys(distances).reduce((a, b) => distances[a] < distances[b] ? a : b);

            let targetLeft, targetTop;
            switch (closestCorner) {
                case 'topLeft':
                    targetLeft = boundaryLeft;
                    targetTop = boundaryTop;
                    break;
                case 'topRight':
                    targetLeft = boundaryRight - videoplayer.offsetWidth;
                    targetTop = boundaryTop;
                    break;
                case 'bottomLeft':
                    targetLeft = boundaryLeft;
                    targetTop = boundaryBottom - videoplayer.offsetHeight;
                    break;
                case 'bottomRight':
                    targetLeft = boundaryRight - videoplayer.offsetWidth;
                    targetTop = boundaryBottom - videoplayer.offsetHeight;
                    break;
            }

            videoplayer.style.left = `${targetLeft}px`;
            videoplayer.style.top = `${targetTop}px`;
        });
    </script> -->

    <div class="baldo"></div>
    <script>
        window.addEventListener('resize', () => document.querySelector('.baldo').style.scale = `${window.innerHeight * 0.62 / 990}`)
    </script>

    <div class="hits"></div>

    <div class="fon-sky">

        <div class="fon-clouds-1"></div>

        <div class="fon-clouds-2"></div>

    </div>

    <div class="fon-trees"></div>

    <div class="fon-forest"></div>

    <div class="fon-tree"></div>

    <div class="fon-lawn"></div>

    <div class="pen">

        

        <div class="chock-infinity"></div>

        <!-- <div class="chock-left-crack"></div>

        <div class="chock-right-crack"></div> -->

    </div>
    <script>
        window.addEventListener('resize', () => document.querySelector('.pen').style.scale = `${window.innerHeight * 0.152 / 165}`);
    </script>

    <div class="fon-grass-flower-2"></div>

    <div class="fon-grass-flower-3"></div>

    <div class="fon-grass-flower"></div>

    <div class="fon-grass">

        <div class="fon-grass-1"></div>

        <div class="fon-grass-2"></div>

        <div class="fon-grass-3"></div>

        <div class="fon-grass-4"></div>

        <div class="fon-grass-5"></div>

    </div>

    <div class="poof"></div>

    

    <div class="bottom-bg-btns">

        <div class="bottom-btns upgrade" onclick="document.querySelector('#upgrade-modal').showModal();"></div>

        <div class="bottom-btns quests" onclick="document.querySelector('#quests-modal').showModal(); initializeQuestSystem();"></div>

        <div class="bottom-btns guild"></div>

        <div class="bottom-btns profile" onclick="document.querySelector('#profile-modal').showModal();"></div>

    </div>







<dialog id="profile-modal">

    <div class="profile-modal-body">

      <!-- <div class="modal-profile-image">

        <div class="modal-profile-photo"></div>

      </div> -->

      <div class="modal-name-profile">

          <username>UserName</username>

      </div>

      

      <div class="modal-baldo-earnings"></div>

      <div class="modal-referral-link">
          <div class="modal-referral-link-wrap"></div>
          <span></span>

        <div class="modal-referral-info" onclick="document.querySelector('.modal-referral-info-popup').style.display = 'block';"></div>

      </div>

      <div class="modal-referral-info-popup">

        <div class="modal-referral-info-img">

            <div class="modal-referral-info-close" onclick="document.querySelector('.modal-referral-info-popup').style.display = 'none';"></div>

        </div>

        <div class="confirm-boost-close-overlay" onclick="document.querySelector('.modal-referral-info-popup').style.display = 'none';"></div>

        </div>

      <div class="modal-referral-earnings"></div>

    </div>

    

    <div class="settings-modal-body" hidden>

        <div class="modal-settings-music">

            <div class="music-switch" onclick='music_switch(this);'></div>

        </div>

        <div class="modal-settings-sound">

            <div class="sound-switch" onclick='sound_switch(this);'></div>

        </div>
        <!-- <div class="modal-settings-clip">

            <div class="clip-switch" onclick='clip_switch(this);'></div>

        </div> -->

        <div class="modal-settings-language"></div>

        <div class="modal-settings-wiki" onclick="document.querySelector('#profile-modal').close(); showWikiModal()"></div>

    </div>

  <div class="modal-nazad" onclick="document.querySelector('#profile-modal').close(); if (localStorage.getItem('energy') > 0) {global_animate_flag=true;}"></div>

  <div class="modal-profile-btn-profile" onclick="

    document.querySelector('.settings-modal-body').style.display = 'none';

    document.querySelector('.profile-modal-body').style.display = 'flex';

    document.querySelector('.modal-profile-btn-settings').style.backgroundImage = 'url(img/ui/profile/btns/settings_passive.png)';

    this.style.backgroundImage = 'url(img/ui/profile/btns/profile_active.png)';"></div>

  

  <div class="modal-profile-btn-settings" onclick="

    document.querySelector('.profile-modal-body').style.display = 'none';

    document.querySelector('.settings-modal-body').style.display = 'block';

    document.querySelector('.modal-profile-btn-profile').style.backgroundImage = 'url(img/ui/profile/btns/profile_passive.png)';

    this.style.backgroundImage = 'url(img/ui/profile/btns/settings_active.png)';"></div>

</dialog>

<div id="wiki-modal" hidden>
    <div class="wiki-modal-timeline">
        <div class="wiki-modal-timeline-item">
            <div class="wiki-modal-timeline-progress"></div>
        </div>
        <div class="wiki-modal-timeline-item">
            <div class="wiki-modal-timeline-progress"></div>
        </div>
        <div class="wiki-modal-timeline-item">
            <div class="wiki-modal-timeline-progress"></div>
        </div>
    </div>
    <div class="wiki-modal-slide active" style="background-image: url(img/ui/wiki/wiki_1.png);"></div>

    <div class="wiki-modal-slide" style="background-image: url(img/ui/wiki/wiki_2.png);"></div>

    <div class="wiki-modal-slide" style="background-image: url(img/ui/wiki/wiki_3_content.png), url(img/ui/wiki/wiki_3_bg.png); background-size: 90% auto, 100% 100%;"></div>

    <div class="wiki-modal-btn-prev wiki-modal-btn"></div>

    <div class="wiki-modal-btn-next wiki-modal-btn"></div>

</div>

<script>
    let currentSlide = 0;
    let timelineInterval;
    const slideDuration = 5000;
    let isHoldingPrev = false;
    let isHoldingNext = false;
    let startTime;
    let elapsedTime = 0;

    function updateSlides() {
        document.querySelectorAll('.wiki-modal-slide').forEach((slide, index) => {
            slide.classList.toggle('active', index === currentSlide);
        });
        updateProgressBars();
    }

    function updateProgressBars() {
        document.querySelectorAll('.wiki-modal-timeline-progress').forEach((progress, index) => {
            progress.style.transition = 'none';
            if (index < currentSlide) {
                progress.style.width = '100%';
            } else if (index === currentSlide) {
                progress.style.width = '0';
                setTimeout(() => {
                    progress.style.transition = `width ${slideDuration}ms linear`;
                    progress.style.width = '100%';
                }, 10);
            } else {
                progress.style.width = '0';
            }
        });
    }

    function startTimeline() {
        if (timelineInterval) clearInterval(timelineInterval);
        
        startTime = new Date();
        timelineInterval = setInterval(() => {
            if (currentSlide < document.querySelectorAll('.wiki-modal-slide').length - 1) {
                currentSlide++;
                updateSlides();
            } else {
                document.querySelector('#wiki-modal').hidden = true;
                currentSlide = 0;
                updateSlides();
            }
            startTime = new Date();
        }, slideDuration - elapsedTime);
    }

    function pauseTimeline() {
        if (timelineInterval) clearInterval(timelineInterval);
        elapsedTime += new Date() - startTime;
        document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.transition = 'none';
    }

    function 
    resumeTimeline() {
        let remainingDuration = slideDuration - elapsedTime;
        console.log(document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.width)
        document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.transition = `width ${remainingDuration}ms linear`;
        document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.width = '100%';
        startTimeline();
        elapsedTime = 0;
    }

    function onNextClick() {
        if (!isHoldingNext) {
            if (currentSlide < document.querySelectorAll('.wiki-modal-slide').length - 1) {
                currentSlide++;
            } else {
                document.querySelector('#wiki-modal').hidden = true;
                currentSlide = 0;
            }
            updateSlides();
            startTimeline();
        }
    }

    function onPrevClick() {
        if (!isHoldingPrev) {
            if (currentSlide > 0) {
                currentSlide--;
            } else {
                document.querySelector('#wiki-modal').hidden = true;
            }
            updateSlides();
            startTimeline();
        }
    }

    let widthT;

    function handleTouchStart(button) {
        widthT = document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.width;
        if (button === 'next') {
            isHoldingNext = true;
        } else if (button === 'prev') {
            isHoldingPrev = true;
        }
        pauseTimeline();
    }

    function handleTouchEnd(button) {
        if (button === 'next') {
            isHoldingNext = false;
        } else if (button === 'prev') {
            isHoldingPrev = false;
        }

        document.querySelectorAll('.wiki-modal-timeline-progress')[currentSlide].style.width = widthT
        resumeTimeline();
    }

    document.querySelector('.wiki-modal-btn-next').addEventListener('touchstart', () => handleTouchStart('next'));
    document.querySelector('.wiki-modal-btn-next').addEventListener('touchend', () => handleTouchEnd('next'));
    document.querySelector('.wiki-modal-btn-prev').addEventListener('touchstart', () => handleTouchStart('prev'));
    document.querySelector('.wiki-modal-btn-prev').addEventListener('touchend', () => handleTouchEnd('prev'));

    document.querySelector('.wiki-modal-btn-next').addEventListener('click', onNextClick);
    document.querySelector('.wiki-modal-btn-prev').addEventListener('click', onPrevClick);

    function showWikiModal() {
        document.querySelector('#wiki-modal').hidden = false;
        currentSlide = 0;
        updateSlides();
        startTimeline();
    }
</script>



<dialog id="quests-modal">

    <div class="modal-quests-btn-daily disabled" onclick="

        // document.querySelector('.modal-quests-daily').removeAttribute('hidden');

        // document.querySelector('.modal-quests-weekly').setAttribute('hidden', true);

        // document.querySelector('.modal-quests-main').setAttribute('hidden', true);

        // this.classList.add('active');

        // document.querySelector('.modal-quests-btn-weekly').classList.remove('active');

        // document.querySelector('.modal-quests-btn-main').classList.remove('active');

    "></div>

    <div class="modal-quests-btn-weekly disabled" onclick="

        // document.querySelector('.modal-quests-weekly').removeAttribute('hidden');

        // document.querySelector('.modal-quests-daily').setAttribute('hidden', true);

        // document.querySelector('.modal-quests-main').setAttribute('hidden', true);

        // this.classList.add('active');

        // document.querySelector('.modal-quests-btn-daily').classList.remove('active');

        // document.querySelector('.modal-quests-btn-main').classList.remove('active');

    "></div>

    <div class="modal-quests-btn-main active" onclick="

        document.querySelector('.modal-quests-main').removeAttribute('hidden');

        document.querySelector('.modal-quests-daily').setAttribute('hidden', true);

        document.querySelector('.modal-quests-weekly').setAttribute('hidden', true);

        this.classList.add('active');

        document.querySelector('.modal-quests-btn-daily').classList.remove('active');

        document.querySelector('.modal-quests-btn-weekly').classList.remove('active');

    "></div>

    <div class="modal-quests-daily modal-quests-list" hidden>

    </div>
    <template id="quest-template">
        <div class="modal-quests-item">
            <img src="" alt="" class="modal-quests-item-img">
            <div class="modal-quests-item-wrapper">
                <a href="#" class="modal-quests-item-link-wrap"></a>
                <div class="modal-quests-item-text"></div>
                <div class="modal-quests-item-btn" onclick=""></div>
            </div>
        </div>
    </template>



    <div class="modal-quests-weekly modal-quests-list" hidden>

    </div>



    <div class="modal-quests-main modal-quests-list">
    </div>

    <div class="modal-quests-btn-nazad" onclick="document.querySelector('#quests-modal').close(); if (localStorage.getItem('energy') > 0) { global_animate_flag = true; }"></div>

</dialog>

<dialog id="guild-modal">

  <div class="modal-guild-close" onclick="document.querySelector('#guild-modal').close(); if (localStorage.getItem('energy') > 0) { global_animate_flag = true; }"></div>

  

  <div class="modal-guild-btn-nazad" style="display: none;" onclick="goBack()"></div>



  <div class="modal-guild-first">

    <div class="modal-guild-main-btns join-squad" onclick="showModalSection('modal-guild-list', this)"></div>

    <div class="modal-guild-main-btns create-squad" onclick="showModalSection('modal-guild-create', this)"></div>

  </div>

  

  <div class="modal-guild-create" hidden>

    <input type="text" class="modal-guild-main-btns input-name-squad" placeholder="Clan name">

    <div class="modal-guild-main-btns caution-squad"></div>

    <label for="avatar-clan-upload" class="modal-guild-main-btns input-image-squad"></label>

    <input id="avatar-clan-upload" type="file" accept=".png, .jpg">

    <div class="modal-guild-main-btns btn-create-squad"></div>

  </div>



  <div class="modal-guild-list" hidden>

    <div class="squad-list-heading"></div>

    <div class="squad-list-container">

        <div class="squad-list-item">

            <img src="img/shield.png" alt="" class="squad-list-ava">

            <div class="squad-list-wrapper">

                <div class="squad-list-name">Clan Name</div>

                <div class="squad-list-text">Ebaldo earnings</div>

                <div class="squad-list-count">members count</div>

            </div>

            <div class="squad-list-btn-join"></div>

        </div>

    </div>

  </div>

  <div class="modal-guild-owner-panel" hidden>

    <div class="squad-panel-wrapper">

        <img src="img/shield.png" class="modal-guild-panel squad-panel-logo" alt="">

        <div class="modal-guild-panel squad-panel-header">

            <div class="modal-guild-panel squad-panel-number">#11111</div> 

            <div class="modal-guild-panel squad-panel-name">Name</div>

            <div class="modal-guild-panel squad-panel-count">count</div>

        </div>

        <div class="modal-guild-panel squad-panel-earnings"></div>

        <div class="modal-guild-panel leaderboard-squad-panel">

            <div class="leaderboard-squad-heading"></div>

            <div class="leaderboard-squad-item">

                <div class="leaderboard-squad-number">1</div>

                <img src="img/nophoto.png" class="leaderboard-squad-avatar">

                <div class="leaderboard-squad-wrapper">

                    <div class="leaderboard-squad-name">Nae</div>

                    <div class="leaderboard-squad-text">Edsgfdsfg</div>

                </div>

            </div>

            <div class="leaderboard-squad-item">

                <div class="leaderboard-squad-number">2</div>

                <img src="img/nophoto.png" class="leaderboard-squad-avatar" alt="">

                <div class="leaderboard-squad-wrapper">

                    <div class="leaderboard-squad-name">Name</div>

                    <div class="leaderboard-squad-text">Edsgfdsfg</div>

                </div>

            </div>

            <div class="leaderboard-squad-item">

                <div class="leaderboard-squad-number">3</div>

                <img src="img/nophoto.png" class="leaderboard-squad-avatar" alt="">

                <div class="leaderboard-squad-wrapper">

                    <div class="leaderboard-squad-name">Name</div>

                    <div class="leaderboard-squad-text">Edsgfdsfg</div>

                </div>

            </div>

            <div class="leaderboard-squad-item">

                <div class="leaderboard-squad-number">1k+</div>

                <img src="img/nophoto.png" class="leaderboard-squad-avatar" alt="">

                <div class="leaderboard-squad-wrapper">

                    <div class="leaderboard-squad-name">Name</div>

                    <div class="leaderboard-squad-text">Edsgfdsfg</div>

                </div>

            </div>

        </div>

        <div class="modal-guild-panel squad-panel-invite-link"></div>

        <div class="modal-guild-panel squad-panel-leave-btn"></div>

    </div>

  </div>

</dialog>



<script>

   function showModalSection(sectionId, button = null) {

  if (button && button.classList.contains('closed')) {

    return;

  }



  document.querySelector('.modal-guild-first').hidden = true;

  document.querySelector('.modal-guild-create').hidden = true;

  document.querySelector('.modal-guild-list').hidden = true;



  document.querySelector(`.${sectionId}`).hidden = false;



  if (sectionId === 'modal-guild-first') {

    document.querySelector('.modal-guild-btn-nazad').style.display = 'none';

  } else {

    document.querySelector('.modal-guild-btn-nazad').style.display = 'block';

  }



  localStorage.setItem('currentModalSection', sectionId);

}



function goBack() {

  const currentSection = localStorage.getItem('currentModalSection');

  

  if (currentSection === 'modal-guild-create' || currentSection === 'modal-guild-list') {

    showModalSection('modal-guild-first');

  }

}



document.addEventListener('DOMContentLoaded', () => {

  showModalSection('modal-guild-first');

});

  </script>





<dialog id="upgrade-modal">

    <div class="upgrades-modal-body">

        

        <div class="modal-upgrades upgrades-axe" onclick="upgrade_and_boost('upg', 'A');">

            <div class="modal-upgrades-axe-animate"></div>

            <text class="upgrades-lvl">lvl. 1</text>

            <div class="upgrades-ebaldo-wrap">

                <text class="upgrades-ebaldo">100 points</text>

            </div>

        </div>

        <div class="modal-upgrades upgrades-energy" onclick="
            if (localStorage.getItem('energy') > 0) {
                upgrade_and_boost('upg', 'E');
            } else {
                document.querySelector('.modal-upgrades-unavailable').style.animation = '0.5s horizontal-shaking';
                setTimeout(() => {
                    document.querySelector('.modal-upgrades-unavailable').style.animation = 'none'
                }, 500)
            }
            ">

            <div class="modal-upgrades-energy-animate"></div>

            <text class="upgrades-lvl">lvl. 1</text>

            <div class="upgrades-ebaldo-wrap">

                <text class="upgrades-ebaldo">100 points</text>

            </div>

        </div>

        <div class="modal-upgrades upgrades-mining" onclick="upgrade_and_boost('upg', 'M');">

            <div class="modal-upgrades-mining-animate"></div>

            <text class="upgrades-lvl">lvl. 1</text>

            <div class="upgrades-ebaldo-wrap">

                <text class="upgrades-ebaldo">100 points</text>

            </div>

        </div>

        <div class="modal-upgrades-unavailable" hidden></div>

    </div>



    <div class="boosts-modal-body" hidden>

        <div class="confirm-boost" onclick="">

            <div class="confirm-boost-img">

                <div class="confirm-boost-close" onclick="document.querySelector('.confirm-boost').style.display = 'none';"></div>

                <div class="confirm-boost-confirm"></div>

            </div>

            <div class="confirm-boost-close-overlay" onclick="document.querySelector('.confirm-boost').style.display = 'none';"></div>

        </div>

        <div class="modal-boosts boost-coffee" onclick="

            if ((localStorage.getItem('balance') >= 40) && (localStorage.getItem('coffee') > 0)){
                if (localStorage.getItem('energy') > 0) {
                    const ebaldoWrap = this.querySelector('.boosts-ebaldo-wrap');
                    document.querySelector('.confirm-boost .confirm-boost-img').style.backgroundImage = 'url(img/ui/upgrade/boosts/confirm_coffee.png)';

                    document.querySelector('.confirm-boost').style.display = 'block';

                    document.querySelector('.confirm-boost-confirm').onclick = function() {

                        upgrade_and_boost('set', 'BC');
                        localStorage.setItem('coffee', Number(localStorage.getItem('coffee')) - 1);
                        ebaldoWrap.classList.add('unavailable')

                        document.querySelector('.confirm-boost').style.display = 'none';

                    };
                } else {
                    document.querySelector('.modal-boosts-unavailable').style.animation = '0.5s horizontal-shaking';
                    setTimeout(() => {
                        document.querySelector('.modal-boosts-unavailable').style.animation = 'none'
                    }, 500)
                }

            }

        ">

            <text class="boosts-available">available 1 times a day</text>

            <div class="boosts-ebaldo-wrap"><span class="boosts-ebaldo">40 points</span></div>

        </div>

        <div class="modal-boosts boost-bone" onclick="

            if ((localStorage.getItem('balance') >= 105 * localStorage.getItem('energy_lvl')) && (localStorage.getItem('bone') > 0)){
                if (localStorage.getItem('energy') > 0) {
                    const ebaldoWrap = this.querySelector('.boosts-ebaldo-wrap');
                    document.querySelector('.confirm-boost .confirm-boost-img').style.backgroundImage = 'url(img/ui/upgrade/boosts/confirm_bone.png)';

                    document.querySelector('.confirm-boost').style.display = 'block';

                    document.querySelector('.confirm-boost-confirm').onclick = function() {

                        upgrade_and_boost('set', 'BB');

                        localStorage.setItem('bone', Number(localStorage.getItem('bone')) - 1);
                        ebaldoWrap.classList.add('unavailable')

                        document.querySelector('.confirm-boost').style.display = 'none';

                    };
                } else {
                    document.querySelector('.modal-boosts-unavailable').style.animation = '0.5s horizontal-shaking';
                    setTimeout(() => {
                        document.querySelector('.modal-boosts-unavailable').style.animation = 'none'
                    }, 500)
                }

            }

        ">

            <text class="boosts-available">available 1 times a day</text>

            <div class="boosts-ebaldo-wrap"><span class="boosts-ebaldo">105 points</span></div>

        </div>

        <div class="modal-boosts boost-steak" onclick="

            if ((localStorage.getItem('balance') >= 150 * localStorage.getItem('energy_lvl')) && (localStorage.getItem('steak') > 0)){
                if (localStorage.getItem('energy') > 0) {
                    const ebaldoWrap = this.querySelector('.boosts-ebaldo-wrap');

                    document.querySelector('.confirm-boost .confirm-boost-img').style.backgroundImage = 'url(img/ui/upgrade/boosts/confirm_steak.png)';

                    document.querySelector('.confirm-boost').style.display = 'block';

                    document.querySelector('.confirm-boost-confirm').onclick = function() {

                        upgrade_and_boost('set', 'BS');

                        localStorage.setItem('steake', Number(localStorage.getItem('steake')) - 1);
                        this.querySelector('.boosts-ebaldo-wrap').classList.add('unavailable');

                        document.querySelector('.confirm-boost').style.display = 'none';

                    };
                } else {
                    document.querySelector('.modal-boosts-unavailable').style.animation = '0.5s horizontal-shaking';
                    setTimeout(() => {
                        document.querySelector('.modal-boosts-unavailable').style.animation = 'none'
                    }, 500)
                }
            }

        ">

            <text class="boosts-available">available 1 times a day</text>

            <div class="boosts-ebaldo-wrap"><span class="boosts-ebaldo">150 points</span></div>

        </div>

        <div class="modal-boosts boost-energy-drink" onclick="
            if ((localStorage.getItem('balance') >= 250 * localStorage.getItem('energy_lvl')) && (localStorage.getItem('energy-drink') > 0)){
                if (localStorage.getItem('energy') > 0) {
                    const ebaldoWrap = this.querySelector('.boosts-ebaldo-wrap');

                    document.querySelector('.confirm-boost .confirm-boost-img').style.backgroundImage = 'url(img/ui/upgrade/boosts/confirm_energy_drink.png)';

                    document.querySelector('.confirm-boost').style.display = 'block';

                    document.querySelector('.confirm-boost-confirm').onclick = function() {

                        upgrade_and_boost('set', 'BE');

                        localStorage.setItem('energy-drink', Number(localStorage.getItem('energy-drink')) - 1);
                        ebaldoWrap.classList.add('unavailable')
                        
                        

                        document.querySelector('.confirm-boost').style.display = 'none';

                    };
                } else {
                    document.querySelector('.modal-boosts-unavailable').style.animation = '0.5s horizontal-shaking';
                    setTimeout(() => {
                        document.querySelector('.modal-boosts-unavailable').style.animation = 'none'
                    }, 500)
                }                    

            }

        ">

            <text class="boosts-available">available 1 times a day</text>

            <div class="boosts-ebaldo-wrap"><span class="boosts-ebaldo">250 points</span></div>

        </div>

        <div class="modal-boosts-unavailable" hidden></div>

    </div>

    

    

    

    

  <div class="modal-upgrade-btn-nazad" onclick="document.querySelector('#upgrade-modal').close(); if (localStorage.getItem('energy') > 0) {global_animate_flag=true;}"></div>

  <div class="modal-upgrade-btn-upgrades" onclick="



    document.querySelector('.upgrades-modal-body').removeAttribute('hidden');

    document.querySelector('.boosts-modal-body').setAttribute('hidden', true);

    document.querySelector('.modal-upgrade-btn-boosts').style.backgroundImage = 'url(img/ui/upgrade/btns/boosts_passive.png)';

    this.style.backgroundImage = 'url(img/ui/upgrade/btns/upgrades_active.png)';"></div>

  

  <div class="modal-upgrade-btn-boosts" onclick="



    document.querySelector('.boosts-modal-body').removeAttribute('hidden');

    document.querySelector('.upgrades-modal-body').setAttribute('hidden', true);

    document.querySelector('.modal-upgrade-btn-upgrades').style.backgroundImage = 'url(img/ui/upgrade/btns/upgrades_passive.png)';

    this.style.backgroundImage = 'url(img/ui/upgrade/btns/boosts_active.png)';"></div>

</dialog>













<!--preload-->

<link rel="preload" as="font" href="SuperSedan.ttf" crossorigin>
<link rel="preload" as="image" href="img/ui/loading/background.jpg">
<link rel="preload" as="image" href="img/ui/loading/done.png">
<link rel="preload" as="image" href="img/ui/loading/undone.png">
<link rel="preload" as="image" href="img/ui/loading/dogs.png">
<link rel="preload" as="image" href="img/ui/loading/foliage.gif">
<link rel="preload" as="image" href="img/ui/panel_icons.png">
<link rel="preload" as="audio" href="music/sound.mp3">
<link rel="preload" as="audio" href="music/axe.mp3">
<link rel="preload" as="image" href="img/fon/forest.png">

<link rel="preload" as="image" href="img/fon/3.png">

<link rel="preload" as="image" href="img/fon/4.png">

<link rel="preload" as="image" href="img/fon/1.png">

<link rel="preload" as="image" href="img/fon/sky.png">

<link rel="preload" as="image" href="img/fon/cloud_1.png">

<link rel="preload" as="image" href="img/fon/cloud_2.png">

<link rel="preload" as="image" href="img/fon/lawn.png">

<link rel="preload" as="image" href="img/fon/tree-right.png">

<link rel="preload" as="image" href="img/hits/plus.png">
<link rel="preload" as="image" href="img/hits/0.png">
<link rel="preload" as="image" href="img/hits/1.png">
<link rel="preload" as="image" href="img/hits/2.png">
<link rel="preload" as="image" href="img/hits/3.png">
<link rel="preload" as="image" href="img/hits/4.png">
<link rel="preload" as="image" href="img/hits/5.png">
<link rel="preload" as="image" href="img/hits/6.png">
<link rel="preload" as="image" href="img/hits/7.png">
<link rel="preload" as="image" href="img/hits/8.png">
<link rel="preload" as="image" href="img/hits/9.png">

<link rel="preload" as="image" href="img/baldo_to_mining.png">

<link rel="preload" as="image" href="img/baldo_mining.png">

<link rel="preload" as="image" href="img/mining_signboard_shadow.gif">

<link rel="preload" as="image" href="img/mining_signboard.gif">

<link rel="preload" as="image" href="img/baldo_step1_idle.png">

<link rel="preload" as="image" href="img/baldo_step2_idle.png">

<link rel="preload" as="image" href="img/baldo_step1.png">

<link rel="preload" as="image" href="img/baldo_step2.png">

<link rel="preload" as="image" href="img/baldo_step3.png">

<link rel="preload" as="image" href="img/pen.png">

<link rel="preload" as="image" href="img/chock.png">

<link rel="preload" as="image" href="img/fon/flower.gif">

<link rel="preload" as="image" href="img/fon/flower_2.gif">

<link rel="preload" as="image" href="img/fon/flower_3.gif">

<link rel="preload" as="image" href="img/fon/grass_1.gif">



<link rel="preload" as="image" href="img/ui/profile/btns/profile_active.png">

<link rel="preload" as="image" href="img/ui/profile/btns/profile_passive.png">

<link rel="preload" as="image" href="img/ui/profile/btns/settings_active.png">

<link rel="preload" as="image" href="img/ui/profile/referal_link_info.png">

<link rel="preload" as="image" href="img/ui/wiki/wiki_1.png">

<link rel="preload" as="image" href="img/ui/wiki/wiki_2.png">

<link rel="preload" as="image" href="img/ui/wiki/wiki_3_bg.png">

<link rel="preload" as="image" href="img/ui/wiki/wiki_3_content.png">

<link rel="preload" as="image" href="img/ui/upgrade/price.png">

<link rel="preload" as="image" href="img/ui/upgrade/price_not.png">

<link rel="preload" as="image" href="img/ui/upgrade/price_unavailable.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/unavailable_message.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/unavailable_message.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/level.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_coffee.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_coffee.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_coffee.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_bone.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_steak.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_energy_drink.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/boosts_passive.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/upgrades_active.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/upgrades_passive.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/boosts_active.png">

<link rel="preload" as="image" href="img/ui/energy_bar.png">

<link rel="preload" as="image" href="img/ui/settings/switch_off.png">
<link rel="preload" as="image" href="img/ui/settings/wiki.png">

<link rel="preload" as="image" href="img/ui/settings/switch_on.png">

<link rel="preload" as="image" href="img/ui/counter.png">

<link rel="preload" as="image" href="img/ui/btn_fon.png">

<link rel="preload" as="image" href="img/ui/profile/fon.png">

<link rel="preload" as="image" href="img/ui/profile/points_earnings.png">

<link rel="preload" as="image" href="img/ui/profile/referral_link.png">

<link rel="preload" as="image" href="img/ui/profile/referral_earnings.png">

<link rel="preload" as="image" href="img/ui/profile/nazad.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/nazad.png">

<link rel="preload" as="image" href="img/ui/profile/btns/settings_passive.png">

<link rel="preload" as="image" href="img/ui/settings/music.png">

<link rel="preload" as="image" href="img/ui/settings/sound.png">

<link rel="preload" as="image" href="img/ui/settings/language.png">

<link rel="preload" as="image" href="img/ui/quests/fon.png">

<link rel="preload" as="image" href="img/ui/quests/btns/daily_passive.png">
<link rel="preload" as="image" href="img/ui/quests/btns/nazad.png">
<link rel="preload" as="image" href="img/ui/quests/item/complete_task.png">
<link rel="preload" as="image" href="img/ui/quests/item/item_background.png">
<link rel="preload" as="image" href="img/ui/quests/item/task_completed.png">
<link rel="preload" as="image" href="img/ui/quests/item/check_task.png">
<link rel="preload" as="image" href="img/quests_icon/telegram.png">
<link rel="preload" as="image" href="img/quests_icon/twitter.png">

<link rel="preload" as="image" href="img/ui/quests/btns/weekly_passive.png">
<link rel="preload" as="image" href="img/ui/quests/btns/weekly_active.png">
<link rel="preload" as="image" href="img/ui/quests/btns/daily_active.png">
<link rel="preload" as="image" href="img/ui/quests/btns/main_active.png">
<link rel="preload" as="image" href="img/ui/quests/btns/main_passive.png">
<link rel="preload" as="image" href="img/ui/quests/btns/weekly_disabled.png">
<link rel="preload" as="image" href="img/ui/quests/btns/daily_disabled.png">


<link rel="preload" as="image" href="img/ui/upgrade/fon.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/confirm_bone.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/bone.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/coffee.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/energy_drink.png">

<link rel="preload" as="image" href="img/ui/upgrade/boosts/steak.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/axe.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/axe.gif">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/energy.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/energy.gif">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/mining.png">

<link rel="preload" as="image" href="img/ui/upgrade/upgrades/mining.gif">


<link rel="preload" as="image" href="img/ui/upgrade/btns/upgrades_passive.png">

<link rel="preload" as="image" href="img/ui/upgrade/btns/boosts_active.png">







</body>

<script src="https://telegram.org/js/telegram-web-app.js"></script>

<script>
let tg = window.Telegram.WebApp;

if (tg.platform == "unknown"){

    username = "user"

    userId = 22113;

}else{

    userId = tg.initDataUnsafe.user.id;

    username = tg.initDataUnsafe.user.username;

    window.Telegram.WebApp.ready();

    window.Telegram.WebApp.expand();

}

document.querySelector('.modal-name-profile > username').innerHTML = username;



let global_click_queue = 0;
let isMiningMode = false;


let socket = new WebSocket("wss://vitabrain.ru:8001");


const refParam = window.Telegram.WebApp.initDataUnsafe.start_param;

socket.onopen = function(e) {   
    if(!refParam && !localStorage.getItem('referral_used')) {
        socket.send(`get:${userId}`);
    } else {
        localStorage.setItem('referral_used', true);
        socket.send(`get:${userId}:${refParam}`);
    }
};

socket.onerror = function(e) {
    global_click_queue++;
    checkAndReconnect();
}



function setUpgrade(selector, item_value) {

    document.querySelector(selector + ' > .upgrades-lvl').innerHTML = "Lvl." + item_value;

    const maxUpgradeLevel = 12;



    if (selector === '.upgrades-energy') {

        const energy = Number(localStorage.getItem('energy'));

        if (energy === 0) {
            document.querySelector(selector + ' .upgrades-ebaldo-wrap').classList.add('unavailable')

        } else {
            document.querySelector(selector + ' .upgrades-ebaldo-wrap').classList.remove('unavailable')

        }

    }



    if (item_value >= maxUpgradeLevel) {

        document.querySelector(selector).onclick = '';

        document.querySelector(selector + ' .upgrades-ebaldo-wrap').classList.add('unavailable');

        document.querySelector(selector + ' .upgrades-ebaldo').innerHTML = 'unavailable';

        document.querySelector(selector + ' > .upgrades-lvl').innerHTML = 'max Lvl';

        return;

    }



    let upgradePrice = 250 * Math.pow(2, item_value - 1);

    document.querySelector(selector + ' .upgrades-ebaldo').innerHTML = upgradePrice + " points";

}



 



function setUpgradeMining() {

    const P = { 2: 3, 3: 7, 4: 15, 5: 30 };

    const maxMiningLevel = 5;

    const currentMiningLevel = Number(localStorage.getItem("mining_lvl"));

    const nextMiningLevel = currentMiningLevel + 1;



    if (currentMiningLevel >= maxMiningLevel) {

        document.querySelector('.upgrades-mining').onclick = '';

        document.querySelector('.upgrades-mining .upgrades-ebaldo-wrap').classList.add('unavailable');

        document.querySelector('.upgrades-mining .upgrades-ebaldo').innerHTML = 'unavailable';

        document.querySelector('.upgrades-mining > .upgrades-lvl').innerHTML = 'max Lvl';

        return;

    }



    const upgradeCosts = {

        500: [1300, 3500, 8400, 18800],

        1000: [2600, 7000, 16900, 37500],

        1500: [3900, 10500, 25300, 56300],

        2000: [5300, 14000, 33800, 75000],

        2500: [6600, 17500, 42200, 93800],

        3000: [7900, 21000, 50600, 112500],

        3500: [9200, 24500, 59100, 131300],

        4000: [10500, 28000, 67500, 150000],

        4500: [11800, 31500, 75900, 168800],

        5000: [13100, 35000, 84400, 187500],

        5500: [14400, 38500, 92800, 206300],

        6000: [15800, 42000, 101300, 225000]

    }



    document.querySelector('.upgrades-mining > .upgrades-lvl').innerHTML = "Lvl." + currentMiningLevel;
    const maxEnergy = Number(localStorage.getItem('max_energy'));
    const upgradeCost = upgradeCosts[maxEnergy][nextMiningLevel - 2];

    

    return upgradeCost;

}


function updateBoostAvailability(selector, item_value) {

    const energy = Number(localStorage.getItem('energy'));

    let availabilityText;

    if (item_value >= 1 && item_value <= 6) {

        availabilityText = `available ${item_value} ${Number(item_value) === 1 ? "time" : "times"} per day.`;

    } else if (item_value === 7) {

        availabilityText = `available per week.`;

    } else {

        availabilityText = "unavailable";

    }

    if (energy === 0 || item_value == 0) {
        document.querySelector(selector + ' .boosts-ebaldo-wrap').classList.add('unavailable');
    } else {
        document.querySelector(selector + ' .boosts-ebaldo-wrap').classList.remove('unavailable');
    }

    document.querySelector(selector + ' > .boosts-available').innerHTML = availabilityText;

}



function handleBoostItem(boostType, selector, item_value) {

    updateBoostAvailability(selector, item_value);

    localStorage.setItem(boostType, item_value);

}



const itemHandlers = {

    "UA": function (item_value) {

        setUpgrade('.upgrades-axe', item_value);

        localStorage.setItem("axe_lvl", item_value);

    },

    "UE": function (item_value) {

        setUpgrade('.upgrades-energy', item_value);

        localStorage.setItem("energy_lvl", item_value);

    },

    "UM": function (item_value) {

        localStorage.setItem("mining_lvl", item_value);

        document.querySelector('.upgrades-mining .upgrades-ebaldo').innerHTML = setUpgradeMining() + " points";

    },

    "BB": function (item_value) {

        handleBoostItem("bone", '.boost-bone', item_value);

    },

    "BC": function (item_value) {

        handleBoostItem("coffee", '.boost-coffee', item_value);

    },

    "BE": function (item_value) {

        handleBoostItem("energy-drink", '.boost-energy-drink', item_value);

    },

    "BS": function (item_value) {

        handleBoostItem("steak", '.boost-steak', item_value);

    },

    "M": function (item_value) {

        localStorage.setItem("max_energy", item_value);

    },

    "R": function (item_value) {
        localStorage.setItem("referral_id", item_value);

        document.querySelector('.modal-referral-link span').innerHTML = item_value;

        document.querySelector('.modal-referral-link-wrap').addEventListener('click', event => {
            window.location.href = `https://t.me/share/url?url=https://t.me/DogeSpikeBot/CHOP?referral=${item_value}&text=Test`
        });

    },

    "G": function (item_value) {

        let canCreateClan = item_value.charAt(0) === '1';

        let isClanLeader = item_value.charAt(0) === '2';

        let guildId = item_value.slice(1);

        localStorage.setItem("guild_id", guildId);

        localStorage.setItem("can_create_clan", canCreateClan ? "true" : "false");

        if (!canCreateClan) {

            document.querySelector('.create-squad').classList.add('closed');

        }



        if (isClanLeader) {

            document.querySelector('.squad-panel-leave-btn').style.display = 'none';

        }



        if (guildId > 0) {

            document.querySelector('.modal-guild-first').hidden = true;

            document.querySelector('.modal-guild-owner-panel').hidden = false;

        }

    }

};



socket.onmessage = function(event) {
    global_coin_flag = true;
    console.log(event.data);

    if (!event.data.includes("Error")) {
        let arr_data;

        if (event.data.length > 30) {
            arr_data = event.data.split(",");
            let list_upgrades = arr_data[0].split(":");
            let parsedData = [];

            list_upgrades.forEach(function (item) {
                let match = item.match(/^([A-Z]+)(\d.*)$/);
                if (match) {
                    let item_type = match[1];
                    let item_value = match[2];

                    if (item_type === "M") {
                        parsedData.unshift({ type: item_type, value: item_value });
                    } else {
                        parsedData.push({ type: item_type, value: item_value });
                    }
                }
            });

            parsedData.forEach(function (data) {
                if (itemHandlers[data.type]) {
                    itemHandlers[data.type](data.value);
                }
            });

            updateShortData(arr_data[1]);
            localStorage.setItem('referral_id', `R1${'0'.repeat(10 - String(userId).length)}${userId}`);
            document.querySelector('.modal-referral-link span').innerHTML = localStorage.getItem('referral_id');
            document.querySelector('.modal-referral-link-wrap').addEventListener('click', event => {
                window.location.href = `https://t.me/share/url?url=https://t.me/DogeSpikeBot/CHOP?startapp=${localStorage.getItem('referral_id')}&text=Let’s chop to earn 💵🪓`
            });
        } else {
            global_click_queue -= 1;
            updateShortData(event.data);
        }

    } else {
        alert(event.data);
    }
};




function updateBoostPrices(balance, energy_lvl) {
    let boost_prices = {
        coffee: 40 * energy_lvl,
        bone: 105 * energy_lvl,
        steak: 150 * energy_lvl,
        'energy-drink': 250 * energy_lvl
    };

    let boosts = ["coffee", "bone", "steak", "energy-drink"];

    boosts.forEach(boost => {
        let price = boost_prices[boost];
        let boostElement = document.querySelector(`.boost-${boost}`);
        let priceElement = boostElement.querySelector('.boosts-ebaldo');
        let wrapElement = boostElement.querySelector('.boosts-ebaldo-wrap');

        if (balance >= price) {
            wrapElement.classList.remove("not");
        } else {
            wrapElement.classList.add("not");
        }

        priceElement.innerHTML = price + " points";
    });
}

function updateUpgradePrices(balance, axe_lvl, energy_lvl) {
    let upgrades = {
        axe: 250 * Math.pow(2, axe_lvl - 1),
        energy: 250 * Math.pow(2, energy_lvl - 1),
        mining: setUpgradeMining()
    };

    Object.keys(upgrades).forEach(upgrade => {
        let price = upgrades[upgrade];
        let upgradeElement = document.querySelector(`.upgrades-${upgrade}`);
        let wrapElement = upgradeElement.querySelector('.upgrades-ebaldo-wrap');

        if (!wrapElement.classList.contains('unavailable')) {
            if (balance >= price) {
                wrapElement.style.backgroundImage = 'url(img/ui/upgrade/price.png)';
            } else {
                wrapElement.style.backgroundImage = 'url(img/ui/upgrade/price_not.png)';
            }
        }
    });
}


function updateShortData(data) {    
    let [energy, balance, axe_power, timer] = data.split(".");
    localStorage.setItem('axe_power', axe_power);

    max_energy = localStorage.getItem('max_energy');
    energy_percent = Math.round((energy / (max_energy / 88)));

    document.getElementsByClassName('energy-bar')[0].style.background = "url(img/ui/energy_bar.png) "+Math.max((energy_percent * 312), 315)+"px 0px";
    document.getElementsByClassName('balance')[0].innerHTML = balance;
    document.querySelector('.energy-bar > text > max-energy-text').innerHTML = max_energy;
    document.querySelector('.energy-bar > text > now-energy-text').innerHTML = energy;

    let energy_lvl = localStorage.getItem('energy_lvl');
    updateBoostPrices(balance, energy_lvl);

    let axe_lvl = localStorage.getItem('axe_lvl');
    updateUpgradePrices(balance, axe_lvl, energy_lvl);

    let axePower = localStorage.getItem('axe_power');
    const touchesArray = Object.keys(touches).filter(key => key !== 'length').map(key => touches[key]);
    touchesArray.forEach((touch) => {
        let div = document.createElement('div');
        div.className = "hit";
        let imagesHTML = '';
        axePower.split('').forEach(number => {
            imagesHTML += `<img src="img/hits/${number}.png" alt="">`;
        });

        div.innerHTML = imagesHTML;
        
        let translateX = (touch.pageX === 0 && touch.pageY === 0) ? '47vw' : `${touch.pageX}px`;
        let translateY = (touch.pageX === 0 && touch.pageY === 0) ? '63vh' : `${touch.pageY}px`;
        div.style.setProperty('--translateX', translateX);
        div.style.setProperty('--translateY', translateY);
        document.querySelector('.hits').appendChild(div);
        
        setTimeout(() => {
            div.remove();
        }, 1000);
    });

    localStorage.setItem("energy", energy);
    localStorage.setItem("balance", balance);

    setUpgrade('.upgrades-energy', localStorage.getItem("energy_lvl"));
    updateBoostAvailability('.boost-bone', localStorage.getItem('bone'));
    updateBoostAvailability('.boost-coffee', localStorage.getItem('coffee'));
    updateBoostAvailability('.boost-energy-drink', localStorage.getItem('energy-drink'));
    updateBoostAvailability('.boost-steak', localStorage.getItem('steak'));

    if (energy == 0) {
        global_animate_flag = false;
        global_coin_flag = false;
        document.querySelector('.modal-upgrades-unavailable').hidden = false;
        document.querySelector('.modal-boosts-unavailable').hidden = false;
    } else {
        document.querySelector('.modal-upgrades-unavailable').hidden = true;
        document.querySelector('.modal-boosts-unavailable').hidden = true; 
    }

    if(timer > 0) {
        if(isMiningMode) {
            stopMiningMode();
        }
        mining_mode(timer);
    } else {
        click_mode();
    }
}




function upgrade_and_boost(command, mode) {
    localStorage.setItem(mode, Number(localStorage.getItem(mode))  + 1);
    
    socket.send(command+':'+userId+':'+mode);

}

const questContainer = document.querySelector('.modal-quests-main.modal-quests-list');
const questTemplate = document.getElementById('quest-template').content;
let questsData = {};

async function loadQuests() {
    const response = await fetch('quests.json', {
        headers: {
            'Pragma': 'no-cache',
            'Cache-Control': 'no-cache'
        }
    });
    questsData = await response.json();
}

function updateQuests(questStatuses) {
    questContainer.innerHTML = ''; 

    questStatuses.forEach(([id, isCompleted]) => {
        const questData = questsData[id];
        if (questData) {
            const questItem = questTemplate.cloneNode(true);
            const img = questItem.querySelector('.modal-quests-item-img');
            const text = questItem.querySelector('.modal-quests-item-text');
            const linkWrap = questItem.querySelector('.modal-quests-item-link-wrap');
            const btn = questItem.querySelector('.modal-quests-item-btn');
            questItem.querySelector('.modal-quests-item').id = `quest-${id}`
            img.src = `img/quests_icon/${questData.icon}`;
            text.textContent = questData.text;
            if (sessionStorage.getItem(`quest_${id}`)) {
                questItem.querySelector('.modal-quests-item').classList.add('modal-quests-item-check');
                btn.onclick = () => requestQuestCheck(id);
            } 
            
            linkWrap.addEventListener('click', (event) => {
                event.preventDefault();

                if (!sessionStorage.getItem(`quest_${id}`)) {
                    sessionStorage.setItem(`quest_${id}`, 'visited');
                    document.querySelector(`#quest-${id}`).classList.add('modal-quests-item-check');
                    btn.onclick = () => requestQuestCheck(id);
                }

                window.location.href = questData.link;
            });

            if (isCompleted) {
                questItem.querySelector('.modal-quests-item').classList.add('modal-quests-item-completed');
                
            }


            questContainer.appendChild(questItem);
        }
    });
}

function requestQuestCheck(id) {
    socket.send(`chk:${userId}:${id}`);
    socket.onmessage = function(e) {
        console.log(e.data)   
        const [questInfo, extraData] = e.data.split('_');
        const questStatuses = questInfo.split(';').map(item => item.split(':').map(Number));
        updateQuests(questStatuses);
        updateShortData(extraData);
    }
    
}

async function initializeQuestSystem() {
    await loadQuests();
    socket.send(`tasks:${userId}`);
    socket.onmessage = function(e) {
        const questStatuses = e.data.split(';').map(item => item.split(':').map(Number));
        updateQuests(questStatuses);
    };
}


let showTimerOverlayTimeout;
let timerInterval;

function mining_mode(time) {
    isMiningMode = true;

    global_animate_flag = false;
    global_coin_flag = false;
    global_click_queue = 0;
    timer = time;

    document.querySelector('.mining-overlay').style.display = 'flex';
    document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_to_mining.png)";
    document.querySelector('.baldo').style.animation = "baldo_to_mining 0.7s steps(7) forwards";

    showTimerOverlayTimeout = setTimeout(() => {
        if (!isMiningMode) return;

        document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_mining.png)";
        document.querySelector('.baldo').style.animation = "baldo_mining 0.7s steps(2) infinite";
    }, 600);

    showTimerOverlayTimeout = setTimeout(() => {
        if (!isMiningMode) return;

        document.querySelector('.mining-overlay-time').style.display = 'block';
        updateTimer();
        timerInterval = setInterval(updateTimer, 1000);
    }, 1100);

    console.log("need sleep 1");
    localStorage.setItem("not_sleep", 1);
}

function stopMiningMode() {
    isMiningMode = false;

    clearTimeout(showTimerOverlayTimeout);
    clearInterval(timerInterval);
}


function formatTime(seconds) {

    let hours = Math.floor(seconds / 3600);

    let minutes = Math.floor((seconds % 3600) / 60);

    let secs = seconds % 60;

    hours = hours < 10 ? '0' + hours : hours;

    minutes = minutes < 10 ? '0' + minutes : minutes;

    secs = secs < 10 ? '0' + secs : secs;



    return `${hours}:${minutes}:${secs} left`;

}



function updateTimer() {
    if (timer >= 0) {

        document.querySelector('.mining-overlay-time').innerText = formatTime(timer);

        timer--;

    } else {

        socket.send("get:"+userId);

        clearInterval(timerInterval);

        if(document.querySelector('.baldo').style.backgroundImage.includes('img/baldo_mining.png')) {
            document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_to_mining.png)";
            document.querySelector('.baldo').style.animation = "baldo_to_mining 0.7s steps(7) forwards reverse";
            setTimeout(() => {
                document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step1_idle.png";
                document.querySelector('.baldo').style.animation = "baldo_idle_play 0.7s steps(2) infinite";
            }, 600)
        }

        global_animate_flag = true;
        document.querySelector('.mining-overlay').style.display = 'none';
    }

}



function click_mode(){
    isMiningMode = false;

    let timerId = setTimeout(() => {

        if (!global_coin_flag){

            setTimeout(() => {

                //document.getElementsByClassName('chock')[0].setAttribute('style','visibility:visible');

                //global_animate_flag = true;

                //global_coin_flag = true;

            }, 600);

        }

    }, 1000);

    localStorage.setItem("not_sleep", 0);

    console.log("click_mode")

}

const soundAxeFiles = [
    'music/axe_1.mp3',
    'music/axe_2.mp3',
    'music/axe_3.mp3',
    'music/axe_4.mp3',
    'music/axe_5.mp3'
];

function getRandomAudio() {
    const randomIndex = Math.floor(Math.random() * soundAxeFiles.length);
    return new Audio(soundAxeFiles[randomIndex]);
}

let audio_background = new Audio('music/sound.mp3');

let audio_axe = new Audio('music/axe.mp3');

audio_background.volume = 0.4;

audio_background.loop = true

let backgroundCurrentTime = 0;

let global_coin_flag = true;

let baldo_live_count = 0;

let global_animate_flag = true;   

 

if (localStorage.getItem('background_music') == null) {

    localStorage.setItem("background_music", "on");

}

if (localStorage.getItem('sound_effect') == null) {

    localStorage.setItem("sound_effect", "on");

}



function music_switch(e){

     if (localStorage.getItem("background_music") == "on"){

        localStorage.setItem("background_music", "off");

        audio_background.pause()

        e.style.backgroundImage = "url(img/ui/settings/switch_off.png)";

    }else{

        audio_background.play()

        e.style.backgroundImage = "url(img/ui/settings/switch_on.png)";

        localStorage.setItem("background_music", "on");

    }

}



function sound_switch(e){

    if (localStorage.getItem("sound_effect") == "on"){

        localStorage.setItem("sound_effect", "off");

        e.style.backgroundImage = "url(img/ui/settings/switch_off.png)";

    }else{

        e.style.backgroundImage = "url(img/ui/settings/switch_on.png)";

        localStorage.setItem("sound_effect", "on");

    }

}

function clip_switch(e){

     if (localStorage.getItem("clip_mode") == "on"){

        localStorage.setItem("clip_mode", "off");

        e.style.backgroundImage = "url(img/ui/settings/switch_off.png)";
        videoplayer.style.display = 'none';

    }else{

        e.style.backgroundImage = "url(img/ui/settings/switch_on.png)";
        videoplayer.style.display = 'block';
        localStorage.setItem("clip_mode", "on");

   }

}

document.addEventListener('visibilitychange', function() {
    if (clicksCount > 0) {
        if (document.hidden) {
            backgroundCurrentTime = audio_background.currentTime;
            removeAudioElement(audio_background);
            if(audio_axe) {
                removeAudioElement(audio_axe);
            }
        } else {
            restoreAudioElement(audio_background, 'music/sound.mp3');
            audio_background.currentTime = backgroundCurrentTime;
        }
    }
});

function removeAudioElement(audioElement) {
    audioElement.pause();
    audioElement.currentTime = 0;
    audioElement.src = '';
    audioElement.load();
}

function restoreAudioElement(audioElement, src) {
    audioElement.src = src;
    audioElement.load();
    audioElement.play();
}


document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step1_idle.png";

document.querySelector('.baldo').style.animation = "baldo_idle_play 0.7s steps(2) infinite";



let clicksCount = 0

let clicks = 0



first_click = true;

    function clickBody() {
        if (global_click_queue <= 50){
            clicks += 1;

            clicksCount++;

            setTimeout(() => {

                clicks = clicks - 1

            }, 1000);

            

            console.log(clicks);

            

            if (first_click){

                first_click = false;

                

                if (localStorage.getItem("background_music") == "off"){

                    document.querySelector('.music-switch').style.backgroundImage = "url(img/ui/settings/switch_off.png)";

                } else if (localStorage.getItem("background_music") == "on"){

                    document.querySelector('.music-switch').style.backgroundImage = "url(img/ui/settings/switch_on.png)";

                    audio_background.play();
                }

                

                

                if (localStorage.getItem("sound_effect") == "off"){

                    document.querySelector('.sound-switch').style.backgroundImage = "url(img/ui/settings/switch_off.png)";

                }else if (localStorage.getItem("sound_effect") == "on"){

                    document.querySelector('.sound-switch').style.backgroundImage = "url(img/ui/settings/switch_on.png)";

                }

            }

            if ((global_coin_flag) && (Number(localStorage.getItem("energy")) > 0) && (Number(localStorage.getItem("not_sleep")) == 0)){

                global_coin_flag = false;

                setTimeout(() => {if (localStorage.getItem("sound_effect") == "on"){audio_axe.play()} global_coin_flag = true;}, 50);

                audio_axe.currentTime = 0;
                if (global_animate_flag) {

                    global_animate_flag = false;
                    

                    document.querySelector('.chock-infinity').style.animation = 'chock_infinity_play steps(29)';

    

                    

                    if (clicks < 15){

                        document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step1.png)";

                        document.querySelector('.baldo').style.animation = "baldo_play 0.5s steps(15)";

                        document.querySelector('.chock-infinity').style.animationDuration = "0.5s"

                    }

                    

                    if ((clicks >= 13) && (clicks <= 17)){

                        document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step2.png)";

                        document.querySelector('.baldo').style.animation = "baldo_play 0.5s steps(15)";

                        document.querySelector('.chock-infinity').style.animationDuration = "0.3s"

                        document.querySelector('.chock-infinity').style.animationIterationCount = "2"

                    }

                    

                    if (clicks > 17){

                        document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step3.png)";

                        document.querySelector('.baldo').style.animation = "baldo_play 0.5s steps(15)";

                        document.querySelector('.chock-infinity').style.animationDuration = "0.2s"

                        document.querySelector('.chock-infinity').style.animationIterationCount = "3"

                    }

                    

                    

                    setTimeout(() => {

                        document.querySelector('.chock-infinity').style.animation = '';

                        if (clicks < 25){

                            document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step1_idle.png)";

                        }else{

                            document.querySelector('.baldo').style.backgroundImage = "url(img/baldo_step2_idle.png)";

                        }

                        document.querySelector('.baldo').style.animation = "baldo_idle_play 0.5s steps(2) infinite";

                        global_animate_flag = true;
       

                    }, 500);

                }

                setTimeout(() => {
                    console.log("click")
                    
                    socket.send("clck:"+userId);

                    global_click_queue += 1;
                    
                    localStorage.setItem("energy", Math.max(0, Number(localStorage.getItem("energy")) - Number(localStorage.getItem('axe_power'))));
                    
                    if(localStorage.getItem('energy') == 0) {
                        if(!isMiningMode) {
                            mining_mode(28800);
                        }
                    }
                }, 50);

                

                /*
                document.getElementsByClassName('poof')[0].style.animation = "";

                

                setTimeout(() => {

                    document.getElementsByClassName('poof')[0].style.animation = "poof_play 0.15s steps(10)";

    

                    document.getElementsByClassName('chock')[0].setAttribute('style','visibility:hidden');

                    document.getElementsByClassName('chock-left-crack')[0].setAttribute('style','visibility:visible');

                    document.getElementsByClassName('chock-right-crack')[0].setAttribute('style','visibility:visible');

                    document.getElementsByClassName('chock-left-crack')[0].style.animation = "chock_left_crack_play 0.8s steps(58)";

                    document.getElementsByClassName('chock-right-crack')[0].style.animation = "chock_left_crack_play 0.8s steps(58)";

    

                }, 200);

                

                setTimeout(() => {

                    document.querySelector('.baldo').style.background = "url(img/baldo_idle.png) 0px 0px";

                    document.querySelector('.baldo').style.animation = "baldo_idle_play 0.7s steps(2) infinite";

                    

                    document.getElementsByClassName('chock-left-crack')[0].setAttribute('style','visibility:hidden');

                    document.getElementsByClassName('chock-right-crack')[0].setAttribute('style','visibility:hidden');

                    

                    

                    

                }, 700);

    

    

                setTimeout(() => {

                    document.getElementsByClassName('pen')[0].style.animation = '';

                }, 1300);

                */

            }

        }else{
            checkAndReconnect();
        }

        console.log(`click ${clicksCount}: ${global_click_queue}`)
    }

    function createHandler(func, timeout) {

        let timer = null;
        let pressed = false;

        return function() {

        if (timer) {
            clearTimeout(timer);
        }

        if (pressed) {
            if (func) {
            func.apply(this, arguments);
            }
            clear();
        } else {
            pressed = true;
            setTimeout(clear, timeout || 500);
        }

        };

        function clear() {
        timeout = null;
        pressed = false;
        }

    }

    let touches = [];

    const ignore = createHandler((e) => e.preventDefault(), 500);
    document.body.addEventListener('touchstart', ignore, { passive: false });

    document.querySelector('.clickable-area').addEventListener("touchstart", function (e) {
        touches = e.touches;
        clickBody();

    });



</script>

</html>
