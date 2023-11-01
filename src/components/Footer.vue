<script setup>
    import { footerText } from "../constants";
</script>


<template>
    <footer id="footer" role="contentinfo">
        <div class="footer__inner">
            <h2 class="footer__text">
                <div>hanul's</div>
                <div>@webs</div>
            </h2>

            <div class="footer__info">
                <div class="left">
                    <div class="title">
                        <a href="https://github.com/chu9400/port2023-vue" target="_blank" rel="noreferrer noopener">code view</a>
                    </div>
                    <p class="desc">이곳에서 소스 코드를 볼 수 있습니다.</p>
                </div>
                <div class="right">
                    <h3>share</h3>
                    <ul>
                        <li v-for="(footer, key) in footerText" :key="key">
                            <a :href="footer.link">{{footer.title}}</a>
                            <em>{{ footer.desc }}</em>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="footer__right">
                &copy; 2023 hanul's<br />

                이 사이트는 VUE를 이용하여 제작하였습니다.
            </div>
        </div>
    </footer>
</template>

<style lang="scss">

#footer{
    font-family: var(--mainKor-font);
}

.footer__inner{
    padding: 16px;
}

.footer__text{
    font-size: 12px;
    text-transform: uppercase;
    border-top: 1px solid var(--black);
    border-bottom: 1px solid var(--black);
    display: flex;
    justify-content: space-between;
}

.footer__info{
    display: flex;
    justify-content: space-between;
    margin: 100px 0px;

    @media (max-width:800px) {
        flex-direction: column;
        margin: 40px 0;
    }

    .left{
        width: 40%;   
        
        @media (max-width:800px) {
            width: 100%;
        }

        .title{
            border-top: 2px solid var(--black);
            border-bottom: 1px solid var(--black);
            padding: 20px 0;
            text-transform: uppercase;
            font-weight: 700;
            background: url(@/assets/img/arrow.svg) no-repeat right 20px;
            transition: all 0.3s;

            &:hover{
                background-color: var(--black400);
                padding-left: 10px;
                border-color: transparent;
                background-position: 95% 20px;
            }

            a:hover {
                text-decoration: underline;
                text-underline-position:under
            }

        }

        .desc{
            font-size: 12px;
            padding-top: 20px;

            @media (max-width:800px) {
                margin-bottom: 40px;
            }
        }
    }


    .right{
        width: 50%;

        @media (max-width:800px) {
            width: 100%;
        }

        h3{
            border-top: 2px solid var(--black);
            font-size: 10px;
            margin-bottom: 40px;
            padding-top: 10px;
            text-transform: uppercase;
        }

        ul{
            border-top: 1px solid var(--black);

            li{
                border-bottom: 1px solid var(--black);
    
                a{
                    display: inline-block;
                    padding: 14px 0;
                    font-size: 14px;
                    text-transform: uppercase;
                }
    
                em{
                    font-size: 12px;
                    padding-left: 10px;
                    opacity: 0;
                    transition: all 0.3s;
                }
    
                &:hover {
                    em {
                        opacity: 1;
                    }
                }
            }
        }

        
    }
}

.footer__right{
    text-align: center;
    text-transform: uppercase;
    font-size: 12px;
    margin-bottom: 20px;
}
</style>